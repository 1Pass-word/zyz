<template>
  <div id="app">
    <nav>
      <h1>微信读书</h1>
    </nav>

    <router-view />
  </div>
</template>

<style lang="less">
* {
  margin: 0;
  padding: 0;
}
nav {
  padding: 30px;
  text-align: center;
  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
