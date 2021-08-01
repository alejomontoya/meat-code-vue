<template>
  <div>
    <router-view />
  </div>
</template>

<style lang="scss">
:root {
  --black: #24272a;
  --grey: #3f454a;
  --grey-ligth: #cfcfcf;
  --gold: #d8ad3d;
  --blue: #009cd9;
  --red: #b72c2c;
}
@import url("https://fonts.googleapis.com/css2?family=Caveat:wght@700&family=Open+Sans:wght@400;700&display=swap");

body {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: "Open Sans", sans-serif;
}

.wrapper {
  max-width: 1536px;
  padding-left: 60px;
  padding-right: 60px;
}
</style>
