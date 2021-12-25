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
			arrowPath: 'M20 0C25.3043 0 30.3914 2.10714 34.1421 5.85786C37.8929 9.60859 40 14.6957 40 20C40 25.3043 37.8929 30.3914 34.1421 34.1421C30.3914 37.8929 25.3043 40 20 40C14.6957 40 9.60859 37.8929 5.85786 34.1421C2.10714 30.3914 0 25.3043 0 20C0 14.6957 2.10714 9.60859 5.85786 5.85786C9.60859 2.10714 14.6957 0 20 0V0ZM11.25 18.75C10.9185 18.75 10.6005 18.8817 10.3661 19.1161C10.1317 19.3505 10 19.6685 10 20C10 20.3315 10.1317 20.6495 10.3661 20.8839C10.6005 21.1183 10.9185 21.25 11.25 21.25H25.7325L20.365 26.615C20.2488 26.7312 20.1566 26.8692 20.0937 27.021C20.0308 27.1729 19.9984 27.3356 19.9984 27.5C19.9984 27.6644 20.0308 27.8271 20.0937 27.979C20.1566 28.1308 20.2488 28.2688 20.365 28.385C20.4812 28.5012 20.6192 28.5934 20.771 28.6563C20.9229 28.7192 21.0856 28.7516 21.25 28.7516C21.4144 28.7516 21.5771 28.7192 21.729 28.6563C21.8808 28.5934 22.0188 28.5012 22.135 28.385L29.635 20.885C29.7514 20.7689 29.8438 20.6309 29.9068 20.4791C29.9698 20.3272 30.0022 20.1644 30.0022 20C30.0022 19.8356 29.9698 19.6728 29.9068 19.5209C29.8438 19.3691 29.7514 19.2311 29.635 19.115L22.135 11.615C22.0188 11.4988 21.8808 11.4066 21.729 11.3437C21.5771 11.2808 21.4144 11.2484 21.25 11.2484C21.0856 11.2484 20.9229 11.2808 20.771 11.3437C20.6192 11.4066 20.4812 11.4988 20.365 11.615C20.2488 11.7312 20.1566 11.8692 20.0937 12.021C20.0308 12.1729 19.9984 12.3356 19.9984 12.5C19.9984 12.6644 20.0308 12.8271 20.0937 12.979C20.1566 13.1308 20.2488 13.2688 20.365 13.385L25.7325 18.75H11.25Z',
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
