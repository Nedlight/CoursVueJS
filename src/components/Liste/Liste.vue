<template>
    <div>
        <ul class="liste">
            <li v-for="(film, index) in myArr" v-bind:key="index">
                <div class="card">
                    Film : {{ film.titre }}
                    <br>
                    Date : {{ film.date }}
                </div>
            </li>
        </ul>
        <p>{{ txt }}</p>
        <div v-on:click="supprFilm" class="btn btn-danger mr-3">Supprime le film</div>
        <div v-on:click="supprTxt" class="btn btn-danger mr-3">Supprime le texte</div>
        <div v-on:click="changeTitre" class="btn btn-danger">Modifie le titre</div>
        <slot>Patientez</slot>
        <slot name="info"></slot>
    </div>
</template>

<script>

    import{bus} from '../../main'
    export default{
        name: 'Liste',
        data(){
            return{
                fruits:['Orange','Papaye','Fraise']
            }
        },
        methods:{
            supprFilm : function(){
                this.myArr.pop()
            },
            supprTxt : function(){
                this.txt=""
            },
            changeTitre : function(){
                // this.$emit('changeTitre',"Mon nouveau Titre")
                bus.$emit('changeTitre','Titre changé avec le bus')
            },
        },
        props: ['myArr', 'txt']
    }

</script>

<style scoped src="./Liste.css">

</style>