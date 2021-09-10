<template>
	<a href="#main" @click="focusMain" class="accesibilty">Skip Header</a>
	<Header />
	<router-view />
	<Footer />
	<Notification />
</template>

<script>
import './scss/index.css'
import Header from './components/UI/Header'
import Footer from './components/UI/Footer'
import Notification from './components/UI/Notification'
export default {
	components: {Header, Footer, Notification},
	methods: {
		focusMain(){
			document.querySelector("#about-me").focus();
		}
	}
}
</script>
