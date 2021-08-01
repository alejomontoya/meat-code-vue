<template>
  <div class="heading">
    <h2>{{ title }}</h2>
    <img src="../assets/heading-shape.png" alt="Heading Shape" srcset="" />
  </div>
</template>

<script>
export default {
  props: {
    title: String,
  },
};
</script>

<style lang="scss">
.heading {
  text-align: center;
  margin-bottom: 70px;
  img {
    padding: 0;
    margin-top: -3%;
    opacity: 0.5;
    @media screen and (max-width: 500px) {
      width: 100%;
      margin-top: -8%;
    }
  }
  h2 {
    position: relative;
    font-family: Caveat;
    font-style: normal;
    font-weight: bold;
    font-size: 80px;
    line-height: 38px;
    margin-bottom: 0;
    z-index: 1;
    @media screen and (max-width: 500px) {
      font-size: 60px;
    }
  }
}
</style>