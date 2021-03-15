<template>
  <div :class='UpdateContainer'>
    <tag :class='UpdateTag'> Update </tag>
    <!-- Pull update infrom from Blog DB -->
    <p :class='body1'> ICF Update — March 1st </p>
    <p :class='body2'> Description of newest IG / ICF update </p>
    <a :class='Link'> Read → </a>
  </div>
</template>

<script>
import { defineComponent } from '@vue/composition-api'

export default defineComponent({
  name: 'Updates',
  data() {
    return {
      UpdateContainer: 'bg-gray-50 rounded-lg border flex space-x-6 p-5 items-center',
      UpdateTag: 'text-white bg-gradient-to-r from-gray-800 to-gray-300 p-2 px-6 rounded-lg',
      body1: 'font-bold',
      body2: 'font-light', 
      Link: 'font-bold', 
    }
  }
})
</script>