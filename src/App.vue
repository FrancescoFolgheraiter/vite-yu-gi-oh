<script>
//importazione app
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import AppFooter from './components/AppFooter.vue';
//importazione axios
import axios from 'axios';
//importazione store
import { store } from './store.js';

export default{
	data() {
		return{
			store
		};
	},
	components:{
		AppHeader,
		AppMain,
		AppFooter
	},
	methods:{

	},
	//utilizzo api 
	created() {
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=15&offset=0').then((response) => {
                this.store.cards = response.data.data
				console.log(this.store.cards)
            });
    }
}

</script>

<template>
	<AppHeader/>
	<AppMain/>
	<AppFooter/>
</template>

<style lang="scss">
@use"assets/scss/main.scss" as *;
body{
	background-color: orange;
}
</style>
