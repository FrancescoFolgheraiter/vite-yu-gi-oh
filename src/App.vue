<script>
//importazione app
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';
import CardLoader from './components/CardLoader.vue'
//importazione axios
import axios from 'axios';
//importazione store
import { store } from './store.js';

export default{
	data() {
		return{
			store,
			flag:false
		};
	},
	components:{
		AppHeader,
		AppMain,
		AppFooter,
		CardLoader
	},
	methods:{
		updateTypeSelcet(query){
			this.store.selectType=[];
			for (let i = 0; i < this.store.cards.length; i++) {
				const archetype = query[i].archetype;
				if(!(query[i].archetype==undefined) && !(this.store.selectType.includes(archetype))){
					this.store.selectType.push(archetype)
				}
			}
			console.log(this.store.selectType)
		},
		updateCards(){

		}		
	},
	//utilizzo api 
	created() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=10').then((response) => {
                this.store.cards = response.data.data
				this.updateTypeSelcet(response.data.data)
				console.log(this.store.cards)
            });
		setTimeout(()=>{
            this.flag = true;
        }, 2000);
    }
}

</script>

<template>
	<div v-if="!(this.flag)">
		<CardLoader/>
	</div>
	<div v-else>
		<AppHeader/>
		<AppMain/>
		<AppFooter/>
	</div>
</template>

<style lang="scss">
@use"assets/scss/main.scss" as *;
body{
	background-color: orange;
}
</style>
