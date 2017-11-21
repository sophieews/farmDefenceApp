<template>
  <div id="home">
    <div class="container">
      <div class="row device-buttons">
        <div data-toggle="buttons">
          <label class="btn btn-primary active">
            <input type="checkbox" checked autocomplete="off"> View All
          </label>
          <label v-for="device in devices" class="btn btn-primary">
            <input type="checkbox" autocomplete="off"> {{ device }}
          </label>
        </div>
      </div>
      <div class="row">
        <h3>Camera 1</h3>

      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: {
    devices: []
  },
  mounted: function() {
//    getDevices();
  },
  methods: {
   getDevices: function() {
     const device_names = ["Camera 1", "Camera 2", "Hatch 1"];
     for (let i = 0; i < device_names.length; i++) {
        this.devices.push(i);
     }
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
</style>
