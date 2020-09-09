<template>
	<div class="form--container">
		<div class="form__input">
			<label for="index">Индекс</label>
			<input type="text" id="index" v-model.trim="index" />
		</div>

		<div class="form__input">
			<label for="country">Страна</label>
			<input type="text" id="country" v-model.trim="country" />
		</div>

		<div class="form__input">
			<label for="area">Область</label>
			<input type="text" id="area" v-model.trim="area" />
		</div>

		<div class="form__input">
			<label for="city">Город*</label>
			<input type="text" id="city" v-model.trim="city" />
		</div>

		<div class="form__input">
			<label for="street">Улица</label>
			<input type="text" id="street" v-model.trim="street" />
		</div>

		<div class="form__input">
			<label for="house">Дом</label>
			<input type="text" id="house" v-model.trim="house" />
		</div>
	</div>
</template>

<script>
export default {
	name: "ClientFormAdress",
	data() {
		return {
			index: "",
			country: "",
			area: "",
			city: "",
			street: "",
			house: "",
		};
	},
};
</script>