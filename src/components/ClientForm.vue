<template>
	<form class="form">
		<h2 class="form-title">Создание клиента</h2>

		<div class="form__input">
			<label for="lastName">Фамилия</label>
			<input type="text" id="lastName" v-model.trim="lastName" />
		</div>

		<div class="form__input">
			<label for="firstname">Имя</label>
			<input type="text" id="firstName" v-model.trim="firstName" />
		</div>

		<div class="form__input">
			<label for="middleName">Отчество</label>
			<input type="text" id="middleName" v-model.trim="middleName" />
		</div>

		<div class="form__input">
			<label for="birthDate">Дата рождения</label>
			<input type="date" id="birthDate" v-model="birthDate" />
		</div>

		<div class="form__input">
			<label for="phoneNumber">Номер телефона</label>
			<input type="tel" id="phoneNumber" v-model.trim="phoneNumber" />
		</div>

		<div class="form__input">
			<label for="gender">Пол</label>
			<select id="gender" v-model="gender">
				<option disabled value>Выберите один из вариантов</option>
				<option>Мужской</option>
				<option>Женский</option>
			</select>
		</div>

		<div class="form__input form__input--large">
			<label for="clientGroup">Группа клиентов</label>
			<select id="clientGroup" v-model="clientGroup" multiple>
				<option disabled value>Выберите один или несколько вариантов</option>
				<option>VIP</option>
				<option>Проблемные</option>
				<option>ОМС</option>
			</select>
		</div>

		<div class="form__input">
			<label for="doctor">Лечащий врач</label>
			<select id="doctor" v-model="doctor">
				<option disabled value>Выберите один из вариантов</option>
				<option>Иванов</option>
				<option>Захаров</option>
				<option>Чернышева</option>
			</select>
		</div>

		<div class="form__checkbox">
			<label for="SmsSending">Не отправлять смс</label>
			<input type="checkbox" id="SmsSending" v-model="SmsSending" />
		</div>
	</form>
</template>

<script>
export default {
	name: "ClientForm",
	data() {
		return {
			firstName: "",
			lastName: "",
			middleName: "",
			birthDate: null,
			phoneNumber: "7",
			gender: "",
			clientGroup: [],
			doctor: "",
			SmsSending: true,
		};
	},
};
</script>

<style lang="scss" scoped>
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
	}
</style>
