<template>
  <div class="card">
    <picture class="card__img">
      <img :src="image" :alt="title" />
    </picture>
    <div class="card__body">
      <p class="card__body-title">
        {{ title }}
      </p>
      <p class="card__body-description">
        {{ content }}
      </p>

      <a class="card__body-see-more"> Ver mas</a>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    content: String,
    image: String,
  },
};
</script>

<style lang="scss">
.card {
  width: 270px;
  border-radius: 10px;
  box-shadow: 0px 4px 40px rgba(0, 0, 0, 0.07);
  overflow: hidden;
  &__img {
    & img {
      max-width: 100%;
      object-fit: contain;
      height: 204px;
    }
  }
  &__body {
    padding-left: 26.3px;
    padding-right: 22.79px;
    padding-bottom: 25.7px;
    &-title {
      color: var(--black);
      font-size: 18px;
      font-weight: 700;
      line-height: 24px;
    }
    &-description {
      color: var(--black);
      font-size: 14px;
      font-weight: 400;
      line-height: 24px;
      opacity: 0.5;
    }
    &-see-more {
      display: none;
      color: var(--gold);
      text-transform: uppercase;
      font-size: 15px;
      line-height: 26px;
      font-weight: 700;
      transition: display 0.3s ease-in-out;
      cursor: pointer;
    }
  }

  &:hover {
    .card__body {
      &-title {
        color: var(--gold);
      }
      &-see-more {
        display: block;
      }
    }
  }
}
</style>