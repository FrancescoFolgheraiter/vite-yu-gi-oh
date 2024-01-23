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
		changeType(value){
			this.store.typeActive = value
		}
	}
}

</script>

<template>
	<main>
		<div class="container mt-4">
			<select v-model="store.typeActive" name="typecard" @click="$emit('archetypeSearch')">
				<option name="typecard" :value ="elem" v-for="(elem, i ) in store.selectType" :key="i" @click="changeType(value)">
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
