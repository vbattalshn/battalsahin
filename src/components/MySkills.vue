<template>
	<section id="my-skills" class="container content-title MySkills-page">
		<div class="myskills-card">
			<div tabindex="0" class="skill" v-for="(skill, index) in skills" :key="index">
				<span class="skill-title" v-text="skill.skillTitle"></span>
				<span class="skill-meter">
					<span :style="'width: ' + skill.width + '%'"></span>
				</span>
			</div>
		</div>
	</section>
</template>

<script>
import { Skills } from "/Data.json"

export default {
	data() {
		return {
			skills: Skills
		}
	},
}
</script>

<style></style>
