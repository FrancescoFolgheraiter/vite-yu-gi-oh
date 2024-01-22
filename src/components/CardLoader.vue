<script>
export default{
	data() {
		return{

		};
	},
	components:{
		
	},
	methods:{
		
	}
}

</script>

<template>
	
	<div class = "img-load">
		<img src="https://vignette.wikia.nocookie.net/yugioh/images/9/94/Back-Anime-2.png/revision/latest?cb=20110624090942" alt="Dorso carta">
		<p>Loading</p>
	</div>


</template>


<style lang ="scss" scoped>

.img-load{
	position: relative;
	background-color: rgba($color: #2b2b2bb4, $alpha: 1.0);
	height: 100vh;
	width: 100vw;
	display: flex;
	justify-content: center;
	align-items: center;

	img{
		width:300px;
	}
	
	p{
		position: absolute;
		top:50%;
		left:50%;
		transform:translate(-50%, -50%);
		color:white;
		font-weight: bold;
		font-size: 1.5rem;
		text-transform: uppercase;
	}
}


</style>
