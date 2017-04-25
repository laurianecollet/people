<template>
	<div>
		<preloader v-if="personnages.length <= 0"></preloader>
		<chips :nb="personnages.length"></chips>
		<div class="row">
			<collections v-for="perso in personnages" :perso="perso"></collections>
		</div>
		<div class="row">
			<card @remove="removeListe(perso)" :key="perso.id" v-for="perso in personnages" :perso="perso" class="lighten-1"></card>
		</div>
		<div class="row">
			<form-ajout @add="ajouterPerso($event)"></form-ajout>
		</div>
		<!--Pour tous les v-for mettre une clé :key="personnage.id"-->
	</div>
</template>
<script>
	import Card from './Card'
	import Preloader from './Preloader'
	import Chips from './Chips'
	import Collections from './Collections'
	import Form from './Form'
	export default { // Ca sera toujours export default et un objet 
		name: 'liste', // identifiant au composant
		components: { card: Card, preloader: Preloader, chips: Chips, collections: Collections, formAjout: Form },// je charge le composant dans Hello , nav est la balise
		data() {
			return {
				personnages: [],
			}
		},
		methods: {
			removeListe: function (perso) {
				this.personnages.splice(this.personnages.indexOf(perso), 1);
			},
			ajouterPerso: function (newPerso) {
				console.log(this.personnages)
				this.personnages.push(newPerso);
				console.log('coucou' + newPerso);
				console.log(this.personnages);

			}
		},
		created: function () {
			let url = "https://raw.githubusercontent.com/Symfomany/angu/master/datas/got.json";
			this.$http.get(url).then(function (response) {
				this.personnages = JSON.parse(response.body);
			}, function (error) {
				console.log('Une erreur est survenue');
			});
		},
	}

</script>

<style scoped>

</style>