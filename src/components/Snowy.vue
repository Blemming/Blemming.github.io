<template>
  <div style="position:absolute;top:0px;width:100%;max-width:100vw;overflow:hidden;z-index:0;">
        <lottie :options="defaultOptions"  v-on:animCreated="handleAnimation"/>
  </div>
</template>

<script>
  import Lottie from 'vue-lottie';
  import animationData from '@/assets/snowy.json';

  export default {
    name: 'app',
    components: {
      Lottie
    },
    data() {
      return {
        defaultOptions: {
			animationData,
			},
			animationSpeed:0.7
	}
	},
	mounted(){
		this.anim.setSpeed(this.animationSpeed);
		// this.stop();
	},
    methods: {
      handleAnimation: function (anim) {
        this.anim = anim;
      },

      stop: function () {
        this.anim.stop();
      },

      play: function () {
        this.anim.play();
      },

      pause: function () {
        this.anim.pause();
      }
    }
}
</script>

<style>

</style>