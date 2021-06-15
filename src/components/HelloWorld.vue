<template>
  <div class="p-5">
    <b-row>
      <b-col>
          <div class="form-group">
            <label for="">Ruta folder</label>
            <b-form-input type="text" v-model="ruta_folder"></b-form-input>
          </div>
        </b-col>
      <b-col>
        <b-form-group>
          <label for="">Adjuntar</label>
          <b-form-file
            v-model="archivos"
            drop-placeholder="Drop file here..."
            multiple
          ></b-form-file>
        </b-form-group>
      </b-col>
    </b-row>
    <b-button variant="primary" @click="enviar()">Enviar</b-button>
  </div>
</template>

<script>
const axios = require('axios').default;
export default {
  data:function(){
    return{
      ruta_folder:null,
      archivos:[],
      url:"http://127.0.0.1:3030/api/uploads",

    };
  },
  watch:{
    archivos(){
      
    }
  },
  methods:{
    procesarArchivos(){
      let form_data = new FormData();
      form_data.append('url_folder',this.ruta_folder);
      this.archivos.forEach(arch => {
        form_data.append('file[]',arch);
      });
      return form_data;
    },
    enviar(){
      let form = this.procesarArchivos();
      axios.post(this.url,form).then(res=>{
        console.log(res)
        this.archivos = [];
      });
    }
  }
}
</script>

<style>

</style>