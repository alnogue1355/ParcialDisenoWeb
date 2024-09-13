<template>
    <div>
        <div class="imaganes-grid">
            <div class="items" v-for="Emisora in EmisoraImagenes" :key="Emisora.id">
                <img :src="Emisora.imagen" alt="">
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name:'EmisoraImagenes',
    data() {
        return {
            EmisoraImagenes: []
        }
    },
    created: function() {
        this.GetAlLEmisoras();
    },
    methods: {
        GetAlLEmisoras: async function() {
            let url = "https://cobuses.com.co/APIV2/model/radio.php?dato=getallemisoras";
            let vue = this;
            await this.axios
            .get(url)
            .then(function(response){
                vue.EmisoraImagenes = response.data
                console.log(vue.EmisoraImagenes);
            })
            .catch(function(error){
                console.log("a ocurrido un error",error);
            })
            .finally(function(){
                console.log("La operacion termino");
            })
        }
    },
}
</script>

<style scoped>
    .imaganes-grid{
        width: 100%;
        height: 100%;
        display: grid;
        grid-template-columns: 1fr 1fr 1fr 1fr 1fr 1fr;
        grid-template-rows: 1fr 1fr 1fr;
    }
</style>