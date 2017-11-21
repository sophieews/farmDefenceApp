<template>
  <div id="app">
    <nav class="navbar navbar-expand-md navbar-dark">
      <router-link :to="{path: '/'}" class="navbar-brand abs">{{ farm }}</router-link>
      <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#collapsibleNavbar">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="collapsibleNavbar">
        <ul class="navbar-nav">
          <li class="nav-item">
            <router-link :to="{path: '/'}"  class="nav-link">HOME</router-link>
          </li>
          <li class="nav-item">
            <router-link :to="{path: '/settings'}" class="nav-link">DEVICES</router-link>
          </li>
          <li class="nav-item">
            <router-link :to="{path: '/about'}" class="nav-link">ABOUT</router-link>
          </li>
        </ul>
        <ul class="navbar-nav ml-auto">
          <li class="nav-item">
            <router-link :to="{path: '/profile'}" class="nav-link">MY PROFILE</router-link>
          </li>
          <li class="nav-item">
            <router-link :to="{path: '/'}" class="nav-link">LOGOUT</router-link>
          </li>
        </ul>
      </div>
    </nav>
    <br>
    <router-view></router-view>
  </div>
</template>

<script>
export default {

  name:"app",
  data () {
    return {
      farm: 'FARM 1'
    }
  }
}
</script>

<style>
#app {

}

</style>
