<template>
  <section class="hero">
    <img src="../assets/hero-shape.png" alt="" srcset="" />
    <p>
      El secreto <br />
      de tu cocina
    </p>
  </section>
</template>

<style lang="scss">

.hero {
  position: relative;
  img {
    position: absolute;
    left: -60%;
    top: 55%;
    z-index: -2;
    @media screen and (max-width: 500px) {
      width: 100%;
      transform: scale(2.6);
      top: 80%;
    }
  }
  p {
    font-family: Caveat;
    font-style: normal;
    font-weight: bold;
    font-size: 120px;
    line-height: 100px;
    color: var(--grey);
    @media screen and (max-width: 500px) {
      font-size: 80px;
    }
  }
}
</style>