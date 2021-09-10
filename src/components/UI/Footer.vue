<template>
	<footer role="contentinfo" class="container">
		<nav>
			<ul>
				<li v-for="(socialMedia, index) in socialMedias" :key="index">
					<a :href="socialMedia.Url" target="_blank" class="social-btn" :class="socialMedia.Name">
						<svg width="16" height="16" fill="currentColor" viewBox="0 0 16 16">
							<path :d="socialMedia.Icon" />
						</svg>
					</a>
				</li>
			</ul>
		</nav>
	</footer>
</template>

<script>
import { SocialMedias } from "/Data.json"

export default{
	data(){
		return{
			socialMedias: SocialMedias
		}
	}
}
</script>

