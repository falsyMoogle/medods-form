<template>
	<div id="app">
		<ClientForm />
	</div>
</template>

<script>
import ClientForm from "./components/ClientForm.vue";

export default {
	name: "App",
	components: {
		ClientForm,
	},
};
</script>

<style lang="scss">
	@import "./styles/variables";

	* {
		box-sizing: border-box;
		padding: 0;
		margin: 0;
	}
	body {
		font-size: 16px;
		font-family: Arial, Helvetica, sans-serif;
		background-color: $bg-secondary;
	}
	#app {
		width: 100%;
		display: flex;
		justify-content: center;
		padding-top: 1rem;
	}
	button,
	input {
		outline: none;
	}
</style>
