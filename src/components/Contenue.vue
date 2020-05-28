<template>

    <div class="container mt-5">

        <h1>Notre premier formulaire</h1>
        <form action="">

            <div class="form-group">
                <label for="prenom">Ton prenom</label>
                <input v-model="formData.prenom" type="text" id="prenom" class="form-control">
            </div>

            <div class="form-group">
                <label for="txt">Ton texte</label>
                <textarea v-model="formData.txt" class="form-control" id="txt"></textarea>
            </div>

            <h3>Selectbox</h3>

            <select v-model="formData.select">
                <option v-bind:key="index" v-for="(pays, index) in formData.listePays">{{ pays }}</option>
            </select>

            
            <h3 class="mt-3">Checkbox</h3>

            <div class="form-check">
                <input v-model="formData.checkFruits" value="fraise" id="fraise" type="checkbox" class="form-check-input">
                <label for="fraise">Fraise</label>
            </div>

            <div class="form-check">
                <input v-model="formData.checkFruits" value="pomme" id="pomme" type="checkbox" class="form-check-input">
                <label for="pomme">Pomme</label>
            </div>

            <div class="form-check">
                <input v-model="formData.checkFruits" value="cerise" id="cerise" type="checkbox" class="form-check-input">
                <label for="cerise">Cerise</label>
            </div>


        <button v-on:click.prevent="envoiForm" class="btn btn-primary mt-3">Envoyer les données</button>

        </form>

        <br>

        <div v-if="infoSubmit">


            <h2>Résultats</h2>

            <div class="card p-3">
                <p>Prénom : {{ formData.prenom }}</p>
                <p style="white-space: pre">Texte : {{ formData.txt }}</p>

                <p>Résultat checkbox</p>
                <ul>
                    <li v-bind:key="index" v-for="(fruit, index) in formData.checkFruits">{{ fruit }}</li>
                </ul>

                <p>Choix du select : {{ formData.select }}</p>
            </div>
        </div>
    </div>
</template>

<script>


    export default{
        name:'contenue',
        data(){
            return{
                formData: {
                    prenom:'',
                    txt:'',
                    checkFruits:[],
                    select:'',
                    listePays:['Kanto','Jhoto','Hoenn','Sinnoh','Unys'],
                },
                infoSubmit:false
            }
        },
        methods:{
            envoiForm: function(){
                this.infoSubmit = true;
            }
        }
    }
</script>

<style>

h1{
    margin-top: 100px!important;
}

</style> 