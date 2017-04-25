<template>
	<div class="col s1">
		<ul class="collection">
			<p>{{perso.nom}}</p>
			<li class="collection-item avatar">
				<i class="material-icons circle teal" v-if="perso.sexe === true">person</i>
				<i class="material-icons circle teal" v-else>directions_walk</i>
			</li>
		</ul>
	</div>
</template>
<script>
	export default {
		name: 'collections',
		props: ['perso'],
	}

</script>
<style scoped>

</style>