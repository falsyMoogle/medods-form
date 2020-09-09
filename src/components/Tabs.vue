<template>
	<div class="tabs--container">
		<ul class="tabs">
			<li
				class="tabs__item"
				v-for="tab in tabs"
				:class="{ 'is-active': tab.isActive }"
				:key="tab.name"
				@click.prevent="selectTab(tab)"
			>
				<span>{{ tab.name }}</span>
			</li>
		</ul>

		<div class="tabs__details">
			<slot></slot>
		</div>
	</div>
</template>

<script>
export default {
	data() {
		return { tabs: [] };
	},
	created() {
		this.tabs = this.$children;
	},
	methods: {
		selectTab(selectedTab) {
			this.tabs.forEach((tab) => {
				tab.isActive = tab.name == selectedTab.name;
			});
		},
	},
};
</script>

<style lang="scss" scoped>
	@import "../styles/variables";

	.tabs {
		width: 100%;
		display: flex;
		justify-content: space-between;
		margin: 1rem 0 2rem 0;
		color: $text-primary;
		&__item {
			width: 33%;
			height: 30px;
			position: relative;
			display: flex;
			justify-content: center;
			align-items: center;
			border-radius: 5px;
			list-style: none;
			cursor: pointer;
			transition: background-color 200ms ease, color 200ms ease;
			&:hover {
				background-color: $blue-200;
				color: $white;
			}
		}
		&__details {
			width: 100%;
			height: 100%;
		}
		&--container {
			width: 100%;
		}
	}

	.is-active {
		background-color: $blue-200;
		color: $white;
	}
</style>