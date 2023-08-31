<template>
	<AppHeader />
	<router-view>
	</router-view>
	<AppFooter />
</template>

<script>
  	import AppHeader from './components/AppHeader.vue';
 	import AppFooter from './components/AppFooter.vue';
	// import {store} from "../store.js";
	// import axios from "axios";

	export default {
		data() {
			return {
				// store
			}
		},

		components: {
			AppHeader,
			AppFooter
		},

		props: {

		},

		mounted () {

		},

		created () {

		},

		methods: {

		}
	}
</script>

<style lang="scss">
	@import "bootstrap/scss/bootstrap";
</style>