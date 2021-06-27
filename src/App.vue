<template>
  <div id="app">

  </div>
</template>

<script>
import DailyIframe from '@daily-co/daily-js';

export default {
  data: function ()  {
    return {callFrame: null}
  },
  name: 'App',
  components: {
  },
 async mounted() {
    const wrapper = document.getElementById('app');
    this.callFrame = DailyIframe.createFrame(wrapper, {
      iframeStyle: {
        border: '1px solid black',
        width: '50vw',
        height: '70vh'
      }
    })

    this.callFrame.on('loaded', () => {alert('joining link')})
    this.callFrame.on('left-meeting', console.log);

    this.callFrame.join({url: '', 
    showLeaveButton: true,
})
    
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  height: 100vh;
}
</style>
