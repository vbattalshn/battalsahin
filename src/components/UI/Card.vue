<template>
	<div tabindex="0" class="card-holder">
		<div class="card-image-holder">
			<img :src="require('../../assets/' + Image)" :alt="Title" width="300" height="300" />
		</div>
        <div class="card-description-holder">
            <h3 class="card-title" v-text="Title"></h3>
            <p class="card-description" v-text="Description"></p>
        </div>
	</div>
</template>

<script>
export default {
    props: {Image: String, Title: String, Description: String}
}
</script>