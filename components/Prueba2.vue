<template>
  <div>
    <button @click="onClick()" >Click</button>
	<input v-model="nombrePadre" >
	
	</input>
  </div>
</template>

<script lang="ts">
import Vue from "vue";



export default Vue.extend({
  props: {
    text: {
      type: String,
      required: true,
    },
	value:{
		type:String,
		required:true
	}
  },

  data(){

	  return{
		  nombrePadre:""
	  }
  },

  watch:{
	  nombrePadre () {
		  console.log("Este es el watch")
		  this.$emit("input", this.nombrePadre)
	  }

  },
  
beforeMount(){
	this.nombrePadre = this.value
},

  methods:{
	  onClick () { 
		  console.log("Hola mundo")
		  const cosa = "Cosa"
		  this.$emit("handleName", cosa)
	  },
	}
});
</script>
