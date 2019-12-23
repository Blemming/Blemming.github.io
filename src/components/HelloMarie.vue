<template>
    <div @click="snow" style="position:relative;width:100%;">
        <MerryXmas></MerryXmas>
		<div :class="{'show':merry,'hidden':!merry}" class="show-text" style="z-index:0;position:relative;margin-top:-10vh;text-align:center;">
			<h1>and<br>Happy holidays <br>to a newly future</h1>
			<span style="z-index:999;" >{{(!snowing)?'Grandma':'Nana'}}</span>
		</div>
        <snowy :class="{'show':snowing,'hidden':!snowing}"  class="snowing"></snowy>
    </div>
</template>

<script>
	import MerryXmas from './MerryXmas'
	import Snowy from './Snowy'
  export default {
    name: 'app',
    components: {
	MerryXmas,
	Snowy
	},
	mounted(){
		setTimeout(()=>{
			this.merry = true
		},4000)
	},
	data:()=>({
		merry:false,
		snowing:false
	}),
	methods:{
		snow(){
			this.snowing = !this.snowing;
		}
	}
    
  }
</script>
<style scoped>
.snowing{
	transition:opacity 0.3s cubic-bezier(0.075, 0.82, 0.165, 1);
}
.hidden{
	opacity:0;
}
.show{
	opacity: 1;
}
.show-text{
	transition:opacity 0.3s cubic-bezier(0.075, 0.82, 0.165, 1);
}
h1{
	z-index: 999;
	color:#301d14;
	margin:0px;
	font-family: 'Poiret One', cursive;
}
span{
	border: 0px;
	background-color: transparent;
	color:#ed3e5c;
	font-size: 2.5rem;
	font-family: 'Bowlby One SC', cursive;
}
</style>