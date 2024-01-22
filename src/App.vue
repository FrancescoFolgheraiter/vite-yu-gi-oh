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

	},
	//utilizzo api 
	created() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0').then((response) => {
                this.store.cards = response.data.data
				console.log(this.store.cards)
            });
		setTimeout(()=>{
            this.flag = true;
        }, 2000)
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
