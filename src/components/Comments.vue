<template>
	<section class="container content-title Comments-page">
		<Splide :options="options">
			<SplideSlide class="Comment-card" v-for="comment in comments" :key="comment.id">
				<img :src="comment.Avatar" :alt="comment.Name" class="author-avatar" />
				<p class="Comment">"{{ comment.Comment }}"</p>
				<span class="author-holder">
					<span class="author-name" v-text="comment.Name"></span>
					<span class="author-desc" v-text="comment.Desc"></span>
				</span>
			</SplideSlide>
		</Splide>
	</section>
</template>

<script>
import {Splide, SplideSlide} from '@splidejs/vue-splide'
import '@splidejs/splide/dist/css/themes/splide-skyblue.min.css'
import {Comments} from '/Data.json'

export default {
	data() {
		return {
			comments: Comments,
		}
	},
	components: {
		Splide,
		SplideSlide,
	},
	setup() {
		const options = {
			rewind: true,
			type: 'loop',
			perPage: 3,
			focus: 'center',
			gap: '1rem',
			autoplay: true,
			breakpoints: {
				1024: {
					perPage: 3,
				},
				768: {
					perPage: 2,
				},
				640: {
					perPage: 1,
					gap: '0rem',
				},
			},
		}

		return {options}
	},
}
</script>

<style></style>
