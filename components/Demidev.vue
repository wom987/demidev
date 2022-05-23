<template>
  <div class="w-100">
    <Home/>
    <Skills/>
  </div>
</template>

<script>
import Home from './profile/Home.vue';
import Skills from './profile/Skills.vue';
export default { components: { Home, Skills } }
</script>

<style>
.logo-text {
    font-size: 3rem;
    font-weight: 700;
    margin-top: 15vh;
}
@media (max-width:500px) {
    .logo-text {
    font-size: 1rem;
    font-weight: 700;
    margin-top: 15vh;
}
}
</style>
