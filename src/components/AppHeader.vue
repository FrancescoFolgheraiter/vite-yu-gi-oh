<script>
export default{
	data() {
		return{
			text:"You-Gi-Oh Api"
		};
	},
	components:{
		
	},
	methods:{

	}
}

</script>

<template>
	<header class="bg-white p-3 d-flex align-items-center ">
		<div class="logo">
			<img class="w-100 " src="https://occ-0-2794-2219.1.nflxso.net/dnm/api/v6/LmEnxtiAuzezXBjYXPuDgfZ4zZQ/AAAABdpYalFU9SD9K6dNwu9SlKsNaQ3AIGWFrN_uDy6R7N3TS5DHIatIETtgeqwC0kM01zJyor2znGql_ixTWzVueA-GllV7Hn03ygETN_Nd7oZA.png?r=81f" alt="">
		</div>
		<h1>
			{{ text }}
		</h1>
	</header>
</template>

<style lang ="scss" scoped>
.logo{
	width:300px;
}

</style>
