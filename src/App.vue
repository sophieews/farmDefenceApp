<template>
  <div id="app">
    <nav class="navbar navbar-expand-md bg-dark navbar-dark">
      <router-link :to="{path: '/'}" class="navbar-brand abs">{{ farm }}</router-link>
      <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#collapsibleNavbar">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="collapsibleNavbar">
        <ul class="navbar-nav">
          <li class="nav-item">
            <router-link :to="{path: '/'}"  class="nav-link">Home</router-link>
          </li>
          <li class="nav-item">
            <router-link :to="{path: '/settings'}" class="nav-link">Device Settings</router-link>
          </li>
          <li class="nav-item">
            <router-link :to="{path: '/about'}" class="nav-link">About</router-link>
          </li>
        </ul>
        <ul class="navbar-nav ml-auto">
          <li class="nav-item">
            <router-link :to="{path: '/profile'}" class="nav-link">My Profile</router-link>
          </li>
          <li class="nav-item">
            <router-link :to="{path: '/'}" class="nav-link">Logout</router-link>
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
      farm: 'Farm Name'
    }
  }
}
</script>

<style>
#app {

}

@media (min-width: 768px) {
  .navbar-brand.abs
  {
    position: absolute;
    left: 0;
    width: 100%;
    text-align: center;
    margin: auto;
    z-index: 0;
  }
  .nav-item
  {
    z-index: 1;
  }
}

</style>
