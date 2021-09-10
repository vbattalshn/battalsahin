<template>
	<section class="container content-title WriteMe-page">
		<div class="writeMe-form-holder">
			<label for="Name" class="label">
				<span class="input-name">Adınız:</span>
				<input autocomplete="off" v-model="Name" type="text" id="Name" class="Name input" title="Minimum 3 karakter." />
			</label>
			<label for="number" class="label">
				<span class="input-name">Telefon Numaranız:</span>
				<input autocomplete="off" v-model="PhoneNumber" type="number" id="number" class="number input" title="Minimum 3 karakter." />
			</label>
			<label for="message" class="label">
				<span class="input-name">Mesajınız:</span>
				<textarea autocomplete="off" v-model="Message" name="text" id="message" class="message textarea" title="Minimum 3 karakter."></textarea>
			</label>
			<button @click="checkForm" class="submit-btn" :class="{spinner: isSending}" :disabled="isSending ? '' : isDisabled" v-text="!isSending ? buttonText : ''"></button>
		</div>
	</section>
</template>

<script>
export default {
	data() {
		return {
			isDisabled: true,
			buttonText: 'Çok yakında aktif olacaktır.',
			Name: '',
			PhoneNumber: '',
			Message: '',
			isSending: false,
			closeTime: null
		}
	},
	computed: {
		notification() {
			return this.$store.state.notification
		},
	},
	methods: {
		checkForm() {
			if (this.Name.length >= 3 && this.PhoneNumber.length >= 3 && this.Message.length >= 3) {
				this.isDisabled = true
				this.isSending = true
			} else {
				this.openNoti('info', 'Lütfen tüm alanlar doldurun.')
			}
		},
		openNoti(type, text) {
			if (this.notification.success) {
				this.closeNoti();
				setTimeout(() => {
					this.notificationConfig(true, type, text)
					this.closeTime = setTimeout(() => {
						this.closeNoti();
					}, 3000)
				}, 250);
			} else {
				this.notificationConfig(true, type, text)
				this.closeTime = setTimeout(() => {
					this.closeNoti();
				}, 3000)
			}
		},
		closeNoti() {
			clearTimeout(this.closeTime)
			this.notification.class = 'close'
			setTimeout(() => {
				this.notificationConfig(false, null, null, null)
			}, 250)
		},
		notificationConfig(success, type, text, classes = null){
			this.notification.success = success
			this.notification.type = type
			this.notification.text = text
			this.notification.class = classes
		}
	},
}
</script>

<style></style>
