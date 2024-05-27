<script setup lang="ts">
import { onMounted, onUnmounted } from 'vue';


onMounted(()=>{
  document.addEventListener('click', handleMouseEnter)
  document.addEventListener('mouseleave', handleMouseLeave)
})

onUnmounted(()=>{
  document.removeEventListener('mousemove', handleMouseEnter)
  document.removeEventListener('mouseleave', handleMouseLeave)
})  

function handleMouseEnter(){
  console.log(event.clientX, event.clientY) 
}

function handleMouseLeave(){
  console.log('mouse left window')
}
</script>

<template>
<div>Holding element</div>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
