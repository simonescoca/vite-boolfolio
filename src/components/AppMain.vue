<template>
	<main>
		<div class="container">

			<div class="d-flex justify-content-between flex-wrap my_cards-container">
				<div v-for="project in projects" class="card" style="width: 18rem;">
					<img :src="project.image" class="card-img-top" :alt="project.title">
					<div class="card-body">
						<h5 class="card-title">
							{{ project.title }}
						</h5>
						<p class="card-text">
							{{ project.content.substr(0, 100) }}
						</p>
						<a href="#" class="btn btn-primary">View</a>
					</div>
				</div>
			</div>


		</div>
	</main>
</template>

<script>
	// import {store} from "../store.js";
	import axios from "axios";

	export default {
		data() {
			return {
				projects: [],
				apiUrl: 'http://127.0.0.1:8000/api/projects',
			}
		},

		components: {

		},

		props: {

		},

		mounted () {

		},

		created () {
			this.getPosts()
		},

		methods: {
			getPosts(){
			axios.get(this.apiUrl)
			.then((response)=>{
				console.log(response.data.results.data)
				this.projects = response.data.results.data
			})
			.catch(function(error){
				console.log(error);
			})
		}
		}
	}
</script>

<style lang="scss" scoped>
	.my_cards-container {
		gap: 1rem;
	}
</style>