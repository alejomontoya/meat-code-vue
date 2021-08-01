<template>
  <form ref="form" v-on:submit.prevent="suscribe" class="contact__form">
    <div class="contact__form-control">
      <label for="name">nombre</label>
      <input type="text" name="firstname" required />
    </div>
    <div class="contact__form-control">
      <label for="lastname">apellido</label>
      <input type="text" name="lastname" required />
    </div>
    <div class="contact__form-control">
      <label for="email">mail</label>
      <input type="email" name="email" required />
    </div>
    <div class="contact__form-control">
      <label for="phone">téléfono</label>
      <input type="tel" name="phone" required />
    </div>
    <button class="contact__form-button" :disabled="isSubmit">enviar</button>
  </form>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      isSubmit: false
    }
  },
  methods: {
    async suscribe(e) {
      this.isSubmit = true
      const formData = new FormData(e.currentTarget);
      try {
        const res = await axios.post(
          "https://5eed24da4cbc340016330f0d.mockapi.io/api/newsletter",
          formData
        );
        alert('Su suscripcion ha sido exitosa!')
        this.isSubmit = false
        this.$refs.form.reset()
      } catch (error) {
        alert('ha ocurrido un error!')
      }
    },
  },
};
</script>
<style lang="scss">
.contact__form {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 23px;
  max-width: 780px;
  margin: 0 auto;

  @media screen and (max-width: 500px) {
    padding: 0 10px;
    grid-template-columns: 1fr;
  }
  &-control {
    display: grid;
    label {
      font-style: normal;
      font-weight: bold;
      font-size: 13px;
      line-height: 24px;
      text-transform: uppercase;
      margin-bottom: 2px;
    }

    input {
      padding: 12px 0 11px 22px;
      outline: none !important;
      font-style: normal;
      font-weight: normal;
      font-size: 14px;
      line-height: 24px;
      &:focus {
        border: 1px solid var(--gold);
      }
    }
  }
  &-button {
    grid-column: 1 / 3;
    justify-self: flex-end;
    margin-bottom: 20px;
    width: 170px;
    height: 55px;
    border: none;
    border-radius: 50px;
    background-color: var(--gold);
    color: white;
    font-weight: 700;
    font-size: 15px;
    line-height: 26px;
    cursor: pointer;
    text-transform: uppercase;
    transition: background 0.3s ease-in-out, transform 0.1s ease-in-out;
    &:active {
      transform: scale(0.9);
    }
    &:hover {
      background-color: var(--blue);
    }
    &:disabled {
      background-color: var(--grey-ligth);
      cursor: not-allowed;
    }

    @media screen and (max-width: 500px) {
      grid-column: auto;
    }
  }
}
</style>