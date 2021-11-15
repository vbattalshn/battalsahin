<template>
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
}
</script>
