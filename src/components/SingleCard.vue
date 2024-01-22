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
	<div class="my-card d-flex flex-column align-items-center mb-3">
		<div class = "container-img">
			<img class="w-100" :src="card.card_images[0].image_url"  :alt="card.name">
		</div>
		<div class="bottom-card text-center">
			<div class="mt-2 mb-2 text-white bold">
				{{ card.name }}
			</div>
			<div class="mb-2">
				{{ card.archetype }}
			</div>
		</div>
	</div>
</template>

<style lang ="scss" scoped>

</style>
