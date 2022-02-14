<template>
  <div>
    <p class="
    text-h4
    text-weight-regular
    text-center
    text-green-6
    no-margin
    ">
      olá mundo!
    </p>
    <button @click="mudarTema">Mudar para tema: {{tema.cor}}</button>
  </div>
</template>

<script>
import { useQuasar } from 'quasar'
import { ref } from '@vue/reactivity'

export default {
  name: 'App',
  setup(){
    const $q = useQuasar()
    const tema = ref({
      cor: 'escuro'
    })

    function mudarTema(){
      if(tema.value.cor === 'escuro'){
        $q.dark.set(true)
        tema.value.cor = 'claro'
      }
      else{
        $q.dark.toggle()
        tema.value.cor = 'escuro'
      }
      
    }

    return{
      tema,
      mudarTema
    }
  }
}
</script>

<style>

</style>
