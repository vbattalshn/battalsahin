<template>
	<div class="content-title-holder container">
		<span class="count">
			{{ count }}
		</span>
		<span class="title-content">
			{{ title }}
		</span>
	</div>
</template>

<script>
export default {
	props: {
		count: String,
		title: String,
	},
}
</script>

<style></style>
