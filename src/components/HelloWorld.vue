<template>
  <div>
    <b-row>
              <b-col>
          <b-form-gorup>
            <label for="">Ruta folder</label>
            <b-form-input type="text"></b-form-input>
          </b-form-gorup>
        </b-col>
      <b-col>
        <b-form-group>
          <label for="">Adjuntar</label>
          <b-form-file
            v-model="archivos"
            placeholder="Choose a file or drop it here..."
            drop-placeholder="Drop file here..."
            multiple
          ></b-form-file>
        </b-form-group>
      </b-col>
    </b-row>
  </div>
</template>

<script>

export default {
  data:function(){
    return{

    };
  }
}
</script>

<style>

</style>