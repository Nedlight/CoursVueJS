<template>
    <div class="container mt-5">

        <h1>{{ titre }}</h1>

    <div class="btn btn-outline-primary mr-2" v-on:click="component='Texte1'">Onglet 1</div>
    <div class="btn btn-outline-primary" v-on:click="component='Texte2'">Onglet 2</div>

    <div class="onglets card mb-5">
        <component class="p-5" v-bind:is="component"></component>
    </div>
    <modale v-bind:revele="revele" v-bind:toggleModale="toggleModale"></modale>



    <div v-on:click="toggleModale" class="btn btn-success">Ouvrir le modal</div>
    </div>
</template>

<script>

    import Texte1 from './Texte1'
    import Texte2 from './Texte2'
    import modale from './Modal'

    export default{
        name:'contenue',
        data: function(){
            return{
                myArr : [
                    {titre : 'Inception', date : 2010},
                    {titre : 'Avatar', date : 2009},
                    {titre : 'Seven', date : 1995}
                ],
                txt: 'Hello world',
                titre : 'Je suis le titre',
                toggle1:true,
                toggle2:false,
                component: "Texte1",
                revele : false
            }
        },
        methods:{
            toggleOng1:function(){
                this.toggle1=true
                this.toggle2=false
            },

            toggleOng2:function(){
                this.toggle1=false
                this.toggle2=true
            },
            toggleModale:function(){
                this.revele= !this.revele
            }
        },
        components:{
            'Texte1': Texte1,
            'Texte2': Texte2,
            'modale' : modale
        }
    }
</script>

<style>

h1{
    margin-top: 100px!important;
}

</style>