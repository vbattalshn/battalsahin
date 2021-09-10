<template>
	<div @click="closeNoti" v-if="notification.success" :class="[notification.type, notification.class]" class="notification">
		<span class="notification-icon">
			<svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-info-circle" viewBox="0 0 16 16">
				<path d="M8 15A7 7 0 1 1 8 1a7 7 0 0 1 0 14zm0 1A8 8 0 1 0 8 0a8 8 0 0 0 0 16z" />
				<path v-if="notification.type == 'success'" d="M10.97 4.97a.235.235 0 0 0-.02.022L7.477 9.417 5.384 7.323a.75.75 0 0 0-1.06 1.06L6.97 11.03a.75.75 0 0 0 1.079-.02l3.992-4.99a.75.75 0 0 0-1.071-1.05z" />
				<path v-else-if="notification.type == 'error'" d="M7.002 11a1 1 0 1 1 2 0 1 1 0 0 1-2 0zM7.1 4.995a.905.905 0 1 1 1.8 0l-.35 3.507a.552.552 0 0 1-1.1 0L7.1 4.995z" />
				<path v-else d="m8.93 6.588-2.29.287-.082.38.45.083c.294.07.352.176.288.469l-.738 3.468c-.194.897.105 1.319.808 1.319.545 0 1.178-.252 1.465-.598l.088-.416c-.2.176-.492.246-.686.246-.275 0-.375-.193-.304-.533L8.93 6.588zM9 4.5a1 1 0 1 1-2 0 1 1 0 0 1 2 0z" />
			</svg>
		</span>
		<span class="notification-description">{{ this.notification.text }}</span>
	</div>
</template>

<script>
export default {
	computed: {
		notification() {
			return this.$store.state.notification
		},
	},
	methods: {
		closeNoti() {
			this.notification.class = 'close'
			setTimeout(() => {
				this.notification.success = false
				this.notification.type = null
				this.notification.text = null
				this.notification.class = null
			}, 250)
		},
	},
}
</script>
