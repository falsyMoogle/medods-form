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
	* {
		box-sizing: border-box;
		padding: 0;
		margin: 0;
	}
	#app {
		width: 100%;
		display: flex;
		justify-content: center;
		padding-top: 1rem;
	}
</style>
