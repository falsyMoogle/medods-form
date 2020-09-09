<template>
	<form class="form">
		<h2 class="form-title">Создание клиента</h2>
		<Tabs>
			<Tab name="Клиент" :selected="true">
				<ClientFormDetails />
			</Tab>
			<Tab name="Адрес">
				<ClientFormAdress />
			</Tab>
			<Tab name="Документ">
				<ClientFormDocument />
			</Tab>
		</Tabs>
	</form>
</template>

<script>
import Tabs from "./Tabs";
import Tab from "./Tab";
import ClientFormDetails from "./ClientFormDetails";
import ClientFormAdress from "./ClientFormAdress";
import ClientFormDocument from "./ClientFormDocument";

export default {
	name: "ClientForm",
	components: {
		Tabs,
		Tab,
		ClientFormDetails,
		ClientFormAdress,
		ClientFormDocument,
	},
	data() {
		return {};
	},
};
</script>

<style lang="scss">
	@import "../styles/variables";

	.form {
		width: 100%;
		display: flex;
		flex-direction: column;
		align-items: center;
		max-width: 600px;
		margin: 5px;
		padding: 1rem 0.8rem;
		border-radius: 8px;
		background-color: $bg-primary;
		color: $accent-400;

		&-title {
			padding: 10px 0;
		}

		&__input {
			width: 100%;
			margin-bottom: 10px;
			&:focus-within label {
				color: $blue-200;
			}
			& label {
				display: block;
				margin: 0 0 2px 0.8125rem;
				color: $accent-400;
				transition: color 200ms ease-in-out;
			}
			& input,
			select {
				width: 100%;
				height: 2.3rem;
				line-height: 2.3rem;
				padding: 0 0.8125rem;
				border: 1px solid $accent-400;
				border-radius: 5px;
				transition: border 200ms ease-in-out, box-shadow 200ms ease-in-out;
				&:focus,
				&:hover {
					border: 1px solid $blue-200;
					box-shadow: inset 0px 0px 1px 1px $blue-200;
				}
			}
			& select[multiple] {
				height: auto;
			}
			&--error {
				&:focus-within label {
					color: $error;
				}
				& label {
					color: $error;
				}
				& input,
				select {
					border-color: $error;
					&:focus,
					&:hover {
						border-color: $error;
						box-shadow: inset 0px 0px 1px 1px $error;
					}
				}
				& small {
					display: block;
					color: $error;
				}
			}
		}
		&__checkbox {
			width: 100%;
			height: 2.3rem;
			display: flex;
			align-items: center;
			& label {
				margin-right: 1rem;
			}
		}
		&--container {
			width: 100%;
		}
	}

	//fade animation
	@keyframes fadein {
		from {
			opacity: 0;
		}
		to {
			opacity: 1;
		}
	}
</style>
