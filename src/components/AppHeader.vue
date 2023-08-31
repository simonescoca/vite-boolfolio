<template>
	<nav class="my-4">
        <ul class="d-flex justify-content-center list-unstyled m-0 my_ul">
            <li v-for="link in links">
                <router-link :to="{ name: link.route }">
                    {{ link.name }}
                </router-link>
            </li>
        </ul>
    </nav>
</template>

<script>
	// import {store} from "../store.js";
	// import axios from "axios";

	export default {
		data() {
			return {
				// store
				links : [
					{
						route: 'homepage',
						name: 'Homepage'
					},
					{
						route: 'about',
						name: 'About Us'
					},
					{
						route: 'projects.index',
						name: 'Projects'
					},
				]
			}
		},

		components: {

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

<style lang="scss" scoped>
	.my_ul {
		gap: 2rem;
		font-size: 1.5rem;

		a {
			text-decoration: none;
		}
	}
</style>