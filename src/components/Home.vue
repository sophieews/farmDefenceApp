<template>
  <div id="home">
      <div class="row device-buttons">
        <div data-toggle="buttons">
          <label class="btn btn-primary active">
            <input type="checkbox" checked autocomplete="off"> View All
          </label>
          <label v-for="device in device_names" class="btn btn-primary">
            <input type="checkbox" autocomplete="off"> {{ device }}
          </label>
        </div>
      </div>
      <div class="events-wrapper">
        <div v-on:click="leftClick" class="left-controls" role="button" aria-label="See Previous Modules">
          <b class="fa fa-chevron-left fa-chevron-left-extra" aria-hidden="true"></b>
        </div>
        <!--<div v-for="device in devices" class="row" style="margin: 0em 2em">-->
        <div class="row">
          <div class="col-12" style="padding-left: 3em">
            <h3>Camera 1</h3>
          </div>
          <div class="event-row">
            <ul id="events" style="margin: 0px">
              <!--<li v-for="event in device.events" class="event-card">-->
              <li class="event-card">
                <h2>event 1</h2>
              </li>
              <li class="event-card">
                <h2>event 2</h2>
              </li>
              <li class="event-card">
                <h2>event 3</h2>
              </li>
              <li class="event-card">
                <h2>event 4</h2>
              </li>
              <li class="event-card">
                <h2>event 5</h2>
              </li>
            </ul>
          </div>
        </div>
        <span v-on:click="rightClick" class="right-controls" role="button" aria-label="See Previous Modules">
          <b class="fa fa-chevron-right fa-chevron-right-extra" aria-hidden="true"></b>
        </span>
      </div>
    </div>
</template>

<script>
export default {
  data() {
    return {
      margin: 0,
      device_names: [],
      devices: [
        {
          "name": "Camera 1",
          "events": [
            {"name": "event1"},
            {"name": "event2"},
            {"name": "event3"},
            {"name": "event4"},
            {"name": "event5"},
            {"name": "event6"},
          ]
        },
        {
          "name": "Camera 2",
          "events": [
            {"name": "event1"},
            {"name": "event2"},
            {"name": "event3"},
            {"name": "event4"},
            {"name": "event5"},
            {"name": "event6"},
          ]
        }
      ]
    }
  },
  mounted: function() {
    this.getDevices();
  },
  methods: {
   getDevices: function() {
     const device_names = ["Camera 1", "Camera 2", "Hatch 1"];
     for (let i = 0; i < device_names.length; i++) {
        this.device_names.push(device_names[i]);
     }
    },

    rightClick: function() {
      const events = document.getElementById('events');
      const margin = parseInt(events.style.marginLeft.slice(0, -2));
      const len = 3 * -400;
      if(margin > len) {
        const end = margin - 400;
        this.animateRight(events, margin, end);
      }
    },

    leftClick: function() {
       const events = document.getElementById('events');
       const start = parseInt(events.style.marginLeft.slice(0, -2));
       if(start < 0) {
         const end = start + 400;
         this.animateLeft(events, start, end);
       }
    },

    animateLeft: function(element, start, end) {
      const id = setInterval(frame, 1);
      function frame() {
        if (start >= end) {
          element.style.marginLeft = end + 'px';
          clearInterval(id);
        } else {
          start += 6;
          element.style.marginLeft = start + 'px';
        }
      }
    },

    animateRight: function(element, start, end) {
      const id = setInterval(frame, 1);
      function frame() {
        if (start <= end) {
          element.style.marginLeft = end + 'px';
          clearInterval(id);
        } else {
          start -= 6;
          element.style.marginLeft = start + 'px';
        }
      }
    }
  }


}


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
</style>
