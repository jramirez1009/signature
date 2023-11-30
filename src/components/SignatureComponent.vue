<template>
    <div>
        <VueSignaturePad ref="signaturePad" />
        <textarea v-model="valorFirma"></textarea>
        <button @click="save">Guardar</button>
        <button @click="undo">Deshacer</button>
        <button @click="clear">Limpiar</button>
    </div>
</template>

<script setup>

import {ref} from 'vue'
import {VueSignaturePad} from 'vue-signature-pad'

const signaturePad = ref(null)
const valorFirma = ref('')
const save = () => {
   const {data} = signaturePad.value.saveSignature();
   valorFirma.value = data
 
}
const undo = () => {
    signaturePad.value.undoSignature();    
}

const clear = () => {
    signaturePad.value.clearSignature();    
}

</script>

<style lang="scss" scoped>

</style>