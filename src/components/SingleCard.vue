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
	<div class="my-card">
		
		{{ card.card_images[0].image_url }}
		{{ card.name }}
	</div>
</template>

<style lang ="scss" scoped>
</style>
