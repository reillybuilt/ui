<template>
	<div
		v-observe-visibility="{
			callback: visibilityChanged,
			intersection: {
				threshold,
			},
			once: !multiple,
			throttle,
		}"
	>
		<transition :enter-active-class="enterActiveClass">
			<div v-show="isVisible">
				<slot></slot>
			</div>
		</transition>
	</div>
</template>

<script>
import 'animate.css';
export default {
	props: {
		animation: {
			type: String,
			default: '',
			required: true,
		},
		delay: {
			type: String,
			default: null,
			validator: (v) => !!v,
		},
		multiple: Boolean,
		repeat: {
			type: String,
			default: null,
			validator: (v) => ['1', '2', '3', 'infinite'].includes(v),
		},
		speed: {
			type: String,
			default: null,
			validator: (v) => ['slow', 'slower', 'fast', 'faster'].includes(v),
		},
		threshold: {
			type: Number,
			default: 1,
		},
	},
	data() {
		return {
			isVisible: false,
		};
	},
	computed: {
		enterActiveClass() {
			const { animation, repeat, speed } = this;
			let classList = `animate__animated animate__${animation}`;
			classList += repeat ? ` animate__repeat-${repeat}` : '';
			classList += speed ? ` animate__${speed}` : '';
			return classList;
		},
		throttle() {
			const { delay } = this;
			return !delay ? 0 : +delay;
		},
	},
	methods: {
		visibilityChanged(isVisible, entry) {
			this.isVisible = isVisible;
		},
	},
};
</script>
