<template>
  <div>
    <h1>{{ nombre }}</h1>
    <h1>foo: {{ foo }}</h1>
    <Prueba2 :text="info" @handleName="(pepe)=> onClick(pepe)" v-model="nombre" />
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "IndexPage",
  data() {
    const info = "data";
    const nombre = "Diego";

    return { 
    info,
    nombre };
  },
  computed:{
    foo(){
      // porque aquí no se puede utilizar el this
      return this.nombre
    }
  },

  beforeMount(){
},

  methods:{
    onClick(pepe: string){
      alert(`Hola mundo ${this.nombre}` )
    }
  }
});

   //   @cambiarNombre="(name)=>nombre=name "  

</script>
