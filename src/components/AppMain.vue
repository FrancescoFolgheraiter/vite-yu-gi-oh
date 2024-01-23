<script>
//importazione app single card
import SingleCard from './SingleCard.vue';

//importazione store
import { store } from '../store.js';
export default{
	data() {
		return{
			store
		};
	},
	components:{
		SingleCard
	},
	methods:{

	}
}

</script>

<template>
	<main>
		<div class="container mt-4">
			<select name="" id="">
				<option :value ="elem" v-for="(elem, i ) in store.selectType" :key="i" @click="updateCards()">
					{{elem}}
				</option>
			</select>
		</div>
		<div class="contaier m-5 bg-white p-5">
			<div class="row">
				<div class="col-12 bg-black text-white mb-3">
					Found {{ store.cards.length }} cards
				</div>
					<div v-for="(elem, i ) in store.cards" :key="i" class="col-12 col-sm-6 col-md-2">
						<SingleCard :card="elem"/>
					</div>
			</div>
		</div>
		
	</main>
</template>

<style lang ="scss" scoped>

</style>
