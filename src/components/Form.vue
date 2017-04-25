<template>
	<div>
		<div class="row">
			<form class="col s12">
				<div class="row">
					<div class="input-field col s12">
						<input id="last_name" type="text" class="validate" v-model="newPerso.nom">
						<label for="last_name">Last Name</label>
					</div>
				</div>
				<div class="row">
					<div class="input-field col s12">
						<input id="first_name" type="text" class="validate" v-model="newPerso.prenom">
						<label for="first_name">Firt name</label>
					</div>
				</div>
				<div class="row">
					<div class="input-field col s12">
						<input id="first_name" type="text" class="validate" v-model="newPerso.photo">
						<label for="photo">Photo</label>
					</div>
				</div>
				<p>
					<input name="group1" type="radio" id="test1" v-model="newPerso.sexe" v-bind:value="false" />
					<label for="test1">Femme </label>
				</p>
				<p>
					<input name="group1" type="radio" id="test2" v-model="newPerso.sexe" v-bind:value="true" />
					<label for="test2">Homme</label>
				</p>
				<div class="row">
					<div class="input-field col s12">
						<input id="town" type="text" class="validate" v-model="newPerso.ville">
						<label for="town">Ville</label>
					</div>
				</div>
				<div class="row">
					<div class="input-field col s12">
						<input id="bio" type="text" class="validate" v-model="newPerso.ville">
						<label for="bio">Biographie</label>
					</div>
				</div>
				<div class="row">
					<button @click="addPerso()" class="btn waves-effect waves-light" type="submit" name="action">Envoyer
  				  <i class="material-icons right">send</i>
  				</button>
				</div>
			</form>
		</div>
	</div>
</template>
<script>
	export default { //j'exporte une instance de vueJS
		name: 'form',
		data() {
			return {
				newPerso: {
					nom: '',
					prenom: '',
					photo: '',
					sexe: true,
					ville: '',
					biographie: ''
				},
			}
		},
		methods: {
			addPerso: function () {
				// J'emet un evenement parent qui s'appelle add
				this.$emit('add', this.newPerso);
				this.newPerso = {
					nom: '',
					prenom: '',
					photo: '',
					sexe: true,
					ville: '',
					biographie: '',
				};
			},
		}
	}

</script>
<style scoped>

</style>