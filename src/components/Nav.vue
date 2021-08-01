<template>
  <nav class="nav">
    <img src="../assets/logo.svg" alt="Logo" srcset="" />
    <section class="social">
      <ul class="social__list">
        <li class="social__list-item facebook">
          <img src="../assets/facebook-icon.svg" alt="Facebook" />
        </li>
        <li class="social__list-item instagram">
          <img src="../assets/instagram-icon.svg" alt="Instagram" />
        </li>
        <li class="social__list-item youtube">
          <img src="../assets/youtube-icon.svg" alt="Youtube" />
        </li>
      </ul>
    </section>
  </nav>
</template>
<style lang="scss">
.nav {
  display: flex;
  justify-content: space-between;
  padding-top: 20px;
  @media screen and (max-width: 500px) {
    & > img {
      width: 120px;
    }
  }
  @media screen and (max-width: 375px) {
    display: block;
  }
  .social {
    width: 300px;
    @media screen and (max-width: 500px) {
      width: auto;
    }
    &__list {
      list-style: none;
      display: flex;
      justify-content: space-around;
      &-item {
        width: 62px;
        height: 62px;
        border: 3px solid;
        border-radius: 50%;
        box-sizing: border-box;
        display: flex;
        justify-content: center;
        align-items: center;
        cursor: pointer;
        &.facebook {
          border-color: var(--blue);
        }
        &.instagram {
          border-color: var(--red);
        }
        &.youtube {
          border-color: var(--gold);
        }
        @media screen and (max-width: 500px) {
          width: 55px;
          height: 55px;
          // gap: 10px;
        }
      }
    }
  }
}
</style>