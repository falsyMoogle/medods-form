<template>
	<div class="form--container">
		<div class="form__input">
			<label for="document">Тип документа*</label>
			<select id="document" v-model="document">
				<option disabled value>Выберите один из вариантов</option>
				<option>Паспорт</option>
				<option>Свидетельство о рождении</option>
				<option>Вод. удостоверение</option>
			</select>
		</div>

		<div class="form__input">
			<label for="serialNumber">Серия</label>
			<input type="text" id="serialNumber" v-model.trim="serialNumber" />
		</div>

		<div class="form__input">
			<label for="documentNumber">Номер</label>
			<input type="text" id="documentNumber" v-model.trim="documentNumber" />
		</div>

		<div class="form__input">
			<label for="issuedBy">Кем выдан</label>
			<input type="text" id="issuedBy" v-model.trim="issuedBy" />
		</div>

		<div class="form__input">
			<label for="dateOfIssue">Дата Выдачи*</label>
			<input type="date" id="dateOfIssue" v-model.trim="dateOfIssue" />
		</div>
	</div>
</template>

<script>
export default {
	data() {
		return {
			document: "",
			serialNumber: "",
			documentNumber: "",
			issuedBy: "",
			dateOfIssue: "",
		};
	},
};
</script>