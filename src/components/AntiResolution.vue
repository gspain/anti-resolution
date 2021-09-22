<template>
	<div class="header section">
		<h1>
			<span class="gradient">Anti</span>
			<span class="highlight">New Year's Resolutions</span>
			<span class="sub">for people who just don't give a fuck.</span>
		</h1>
	</div>

	<div class="content section">
		<span class="resolution">
			<span v-if="resolution">{{ resolution }}</span>
			<span v-else>Whoops! This resolution is missing.</span>
		</span>
		<div class="resolution-trigger">
			<button
				class="button"
				type="button"
				name="submit"
				@click.prevent="getResolution()"
			></button>
		</div>
	</div>

	<div class="footer section">
		<p class="copyright">&copy; Copyright 2012 - All Rights Reserved</p>
	</div>
</template>

<script>
import { defineComponent } from "vue";
import Resolutions from "@/assets/resolutions";

export default defineComponent({
	data() {
		return {
			resolution: '',
			resolutions: Resolutions['resolutions'],
		};
	},

	created() {
		this.getResolution();
	},

	methods: {
		getResolution() {
			const idx = Math.floor(this.resolutions?.length * Math.random());
			this.resolution = this.resolutions[idx];
		}
	}
});
</script>
