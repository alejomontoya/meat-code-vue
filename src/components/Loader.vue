<template>
  <div class="loader"></div>
</template>

<style lang="scss">
.loader {
  height: 50px;
  width: 50px;
  border: 3px solid var(--gold);
  border-radius: 50%;
  border-top: none;
  margin: 0 auto;
  animation: loader 1s infinite ease-in-out;
}
@keyframes loader {
  to {
    transform: rotate(360deg);
  }
  from {
    transform: rotate(0)
  }
}
</style>