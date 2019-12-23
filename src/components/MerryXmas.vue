<template>
  <div style="width:90%;max-width:100vw;overflow:hidden;margin:0 auto;">
        <lottie :options="defaultOptions" style="width:170%;margin-left:-35%;margin-right:-35%;"  v-on:animCreated="handleAnimation"/>
  </div>
</template>

<script>
  import Lottie from 'vue-lottie';
  import animationData from '@/assets/merry-christmas.json';

  export default {
    name: 'app',
    components: {
      Lottie
    },
    data() {
      return {
        defaultOptions: {
			animationData,
			loop:false,
			rendererSettings: {
				preserveAspectRatio:'xMinYMin'
			}
			},
			animationSpeed:0.5
	}
	},
	mounted(){
        this.anim.setSpeed(this.animationSpeed);
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