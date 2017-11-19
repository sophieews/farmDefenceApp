<template>
  <div id="app">
    <nav class="navbar navbar-expand-md bg-dark navbar-dark">
      <router-link :to="{name: 'Home'}" class="navbar-brand abs">{{ farm }}</router-link>
      <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#collapsibleNavbar">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="collapsibleNavbar">
        <ul class="navbar-nav">
          <li class="nav-item">
            <router-link :to="{name: 'Home'}"  class="nav-link">Home</router-link>
          </li>
          <li class="nav-item">
            <router-link :to="{name: 'Settings'}" class="nav-link">Device Settings</router-link>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">About</a>
          </li>
          <li>
            <img>
          </li>
        </ul>
        <ul class="navbar-nav ml-auto">
          <li class="nav-item">
            <a class="nav-link" href="#">My Profile</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Logout</a>
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
    width: 100%;
    left: 0;
    text-align: center;
    margin:0 auto;
  }
}

</style>
