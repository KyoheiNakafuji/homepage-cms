<template>
  <div id="app">
    <div v-if="!$route.meta.auth">
      ログイン前のレイアウト
      <div id="nav">
        <router-link to="/">Home</router-link>
        <router-link to="/about">About</router-link>
        <router-link to="/signin">ログイン</router-link>
        <router-link to="/signup">アカウント作成</router-link>
        <router-link to="/confirmCode">コード確認</router-link>
        <router-link to="/signin-mfa">mfa</router-link>
        <router-link to="/dashboard">ダッシュボード</router-link>
      </div>
    </div>
    <div v-else>
      <router-link to="/signout">サインアウト</router-link>
      <router-link to="/dashboard">ダッシュボード</router-link>
      ログイン後のレイアウト
    </div>
    <router-view/>
  </div>
</template>
<style lang="sass">
#app
  font-family: 'Avenir', Helvetica, Arial, sans-serif
  -webkit-font-smoothing: antialiased
  -moz-osx-font-smoothing: grayscale
  text-align: center
  color: #2c3e50

#nav
  padding: 30px
  a
    font-weight: bold
    color: #2c3e50
    &.router-link-exact-active
      color: #42b983
</style>
