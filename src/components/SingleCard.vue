<script>
export default{
	data() {
		return{

		};
	},
	props: {
        card: Object
    },
	components:{
		
	},
	methods:{
		
	}
}

</script>

<template>
	<div class="my-card d-flex flex-column justify-content-center align-items-center">
		<div class = "container-img">
			<img class="w-100" :src="card.card_images[0].image_url"  :alt="card.name">
		</div>
		<div class="bottom-card text-center">
			{{ card.name }}
			{{ card.archetype }}
		</div>
	</div>
</template>

<style lang ="scss" scoped>
.my-card{
	.container-img{
		width:180px;
	}
}
</style>
