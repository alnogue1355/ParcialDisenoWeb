<template>
    <div>
        <div class="contenedorMusica" v-for="ListaMusica in ListaEmisora" :key="ListaMusica.id">
            <li class="lista">
                {{ ListaMusica.nombre }}
            </li>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ListaEmisora',
    data() {
        return {
            ListaEmisora: []
        }
    },
    created: function () {
        this.GetListaEmisora()
    },
    methods: {
        GetListaEmisora: async function () {
            let url = "https://cobuses.com.co/APIV2/model/radio.php?dato=getallgeneros";
            let vue = this;
            await this.axios
                .get(url)
                .then(function (response) {
                    vue.ListaEmisora = response.data;
                    console.log(vue.ListaEmisora);

                })
                .catch(function (error) {
                    console.log("a ocurrido un error", error);
                })
                .finally(function () {
                    console.log("la operacion finalizo");
                })
        }
    }
}
</script>

<style scoped>
.contenedorMusica {
    width: 100%;
    height: 30px;
    display: flex;
    align-items: center;
    flex-direction: column;
}

.contenedorMusica>li {
    width: 70%;
    height: 600px;
    background: #455A64;
    background-position: center;
    color: white;
    margin-top: 50px;
    margin-bottom: 50px;
    border: 2px black solid;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}

.contenedorMusica>li:hover {
    cursor: pointer;
    background: #697A82;
}


</style>