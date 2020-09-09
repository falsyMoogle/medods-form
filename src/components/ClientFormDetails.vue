<template>
	<div class="form--container">
		<div class="form__input" :class="{'form__input--error': $v.lastName.$error}">
			<label for="lastName">Фамилия*</label>
			<input type="text" id="lastName" v-model.trim="$v.lastName.$model" />
			<div class="invalid-feedback" v-if="$v.lastName.$error">
				<small v-if="!$v.lastName.required">Это поле обязательно к заполнению</small>
				<small
					v-if="!$v.lastName.minLength"
				>Поле должно содержать не менее {{$v.lastName.$params.minLength.min}} символов</small>
			</div>
		</div>

		<div class="form__input" :class="{'form__input--error': $v.firstName.$error}">
			<label for="firstname">Имя*</label>
			<input type="text" id="firstName" v-model.trim="$v.firstName.$model" />
			<div class="invalid-feedback" v-if="$v.firstName.$error">
				<small v-if="!$v.firstName.required">Это поле обязательно к заполнению</small>
				<small
					v-if="!$v.firstName.minLength"
				>Поле должно содержать не менее {{$v.firstName.$params.minLength.min}} символов</small>
			</div>
		</div>

		<div class="form__input">
			<label for="middleName">Отчество</label>
			<input type="text" id="middleName" v-model.trim="middleName" />
		</div>

		<div class="form__input" :class="{'form__input--error': $v.birthDate.$error}">
			<label for="birthDate">Дата рождения*</label>
			<input type="date" id="birthDate" v-model="$v.birthDate.$model" />
			<div class="invalid-feedback" v-if="$v.birthDate.$error">
				<small v-if="!$v.birthDate.required">Это поле обязательно к заполнению</small>
				<small v-if="!$v.birthDate.maxAge">Не верный год рождения</small>
			</div>
		</div>

		<div class="form__input" :class="{'form__input--error': $v.phoneNumber.$error}">
			<label for="phoneNumber">Номер телефона*</label>
			<input type="tel" id="phoneNumber" maxlength="11" v-model.trim="$v.phoneNumber.$model" />
			<div class="invalid-feedback" v-if="$v.phoneNumber.$error">
				<small v-if="!$v.phoneNumber.required">Это поле обязательно к заполнению</small>
				<small v-if="!$v.phoneNumber.startNumber">Номер должен начинаться с префикса 7</small>
			</div>
		</div>

		<div class="form__input">
			<label for="gender">Пол</label>
			<select id="gender" v-model="gender">
				<option disabled value>Выберите один из вариантов</option>
				<option>Мужской</option>
				<option>Женский</option>
			</select>
		</div>

		<div
			class="form__input form__input--large"
			:class="{'form__input--error': $v.clientGroup.$error}"
		>
			<label for="clientGroup">Группа клиентов*</label>
			<select id="clientGroup" v-model="$v.clientGroup.$model" multiple>
				<option disabled value>Выберите один или несколько вариантов</option>
				<option>VIP</option>
				<option>Проблемные</option>
				<option>ОМС</option>
			</select>
			<!-- <span>{{$v.clientGroup.$error}}</span> -->
			<div class="invalid-feedback" v-if="$v.clientGroup.$error">
				<small v-if="$v.clientGroup.$error">Это поле обязательно к заполнению</small>
			</div>
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
	</div>
</template>

<script>
import { required, minLength } from "vuelidate/lib/validators";

export default {
	name: "ClientFormDetails",
	data() {
		return {
			firstName: "",
			lastName: "",
			middleName: "",
			birthDate: "",
			phoneNumber: "7",
			gender: "",
			clientGroup: [],
			doctor: "",
			SmsSending: true,
			error: null,
		};
	},
	validations: {
		firstName: {
			required,
			minLength: minLength(2),
		},
		lastName: {
			required,
			minLength: minLength(2),
		},
		birthDate: {
			required,
			maxAge: (age) => new Date(age) <= new Date(),
		},
		phoneNumber: {
			required,
			startNumber: (phoneNumber) => +phoneNumber[0] === 7,
		},
		clientGroup: {
			required,
		},
	},
};
</script>
