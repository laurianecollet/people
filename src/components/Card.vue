<template>
	<div>
		<div class="card s4 col" v-bind:class="{amber: baratheon(perso)}">
			<!--v-bind:class="{amber: "-->
			<div class="card-image">
				<img :src="perso.photo">
				<span class="card-title">{{perso.nom}}</span>
			</div>
			<a @click="removePerso" class="btn-floating btn-large red">
				<i class="material-icons">delete</i>
			</a>
			<div class="card-content">
				<p>{{perso.sexe|sexe}}</p>
				<p>{{perso.biographie}}</p>
			</div>
		</div>
	</div>
</template>
<script>
	export default {
		name: 'card',
		filters: {
			sexe: function (persoSexe) {
				if (persoSexe === true) {
					return "C'est un homme";
				} else {
					return "C'est une femme";
				}
			}
		},
		props: ['perso'], // Tu peux aussi mettre l'objet avec perso { avec un type Object } pour lui imposer un type 
		methods: {
			baratheon: function (perso) {
				let regexBar = new RegExp(/^.*Baratheon.*$/i);
				return regexBar.test(perso.biographie);
			},
			removePerso: function () {
				// J'emet un evenement parent qui s'appelle remove
				this.$emit('remove');
			},
		}
	}

</script>
<style scoped>
	h2 {
		margin: 0px;
	}
	
	.card {
		width: 40%;
	}
	
	.card-content {
		text-align: justify;
	}
	
	.card .card-image img {
		margin-bottom: 20px;
	}
</style>