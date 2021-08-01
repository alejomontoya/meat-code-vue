<template>
  <section class="filter">
    <ul class="filter__list">
      <li
        :class="`filter__list-item ${
          filter.active === filterActive ? 'active' : ''
        }`"
        v-for="(filter, index) in filters"
        :key="index"
        @click="filterArticles(filter.active)"
      >
        <span>{{ filter.label }}</span> <img src="../assets/arrow.svg" alt="" />
      </li>
    </ul>
  </section>
</template>
<script>
export default {
  data() {
    return {
      filterActive: "",
      filters: [
        {
          label: "TODOS",
          active: "",
        },
        {
          label: "PRODUCTOS",
          active: "Productos",
        },
        {
          label: "RECETA",
          active: "Recetas",
        },
        {
          label: "CONSEJO",
          active: "Consejos",
        },
      ],
    };
  },
  methods: {
    filterArticles(filter) {
      this.filterActive = filter;
      this.$emit("filter", filter);
    },
  },
};
</script>
<style lang="scss">
.filter {
  width: 274px;
  height: 319px;
  border-radius: 10px;
  box-shadow: 0px 4px 40px rgba(0, 0, 0, 0.07);
  padding-top: 24px;
  padding-left: 23px;
  padding-right: 24px;
  @media screen and (max-width: 450px) {
    width: auto;
    height: auto;
  }
  &__list {
    list-style: none;
    font-style: normal;
    font-size: 12px;
    line-height: 23px;
    letter-spacing: 0.03em;
    width: 100%;
    padding: 0;
    &-item {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 2em;
      cursor: pointer;
      img {
        display: none;
      }
      &.active {
        img {
          display: block;
        }
        span {
          font-weight: 700;
          color: var(--gold);
        }
      }
    }
  }
}
</style>