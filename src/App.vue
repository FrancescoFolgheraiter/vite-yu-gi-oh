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
		getCardsFromApi(){
			axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php',{
				params:{
					archetype:this.store.typeActive
				}
			})
			.then((response) => {
				this.store.cards = response.data.data
				console.log(this.store.cards)
				console.log(this.store.typeActive)
            })
			.catch((error) => {
                    this.store.cards = [];
			});
		}		
	},
	//utilizzo api 
	created() {
        this.getCardsFromApi();
		axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php').then((response) => {
			for (let i = 0; i < response.data.length; i++) {
				this.store.selectType.push(response.data[i].archetype_name)
				
			}
			console.log("selectType",this.store.selectType)
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
		<AppMain @archetypeSearch="getCardsFromApi()"/>
		<AppFooter/>
	</div>
</template>

<style lang="scss">
@use"assets/scss/main.scss" as *;
body{
	background-color: orange;
}
</style>
