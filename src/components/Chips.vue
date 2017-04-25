<template>
	<div>
		<div class="chip" :class="{teal:teal, 'red lighten-1': red, 'pulse': pulse}">
			<p v-if="nb > 0">Il y a {{ nb }} personnages</p>
			<p v-else>Il y a aucun personnages</p>
		</div>
	</div>
</template>
<script>
	export default {
		name: 'chips',
		computed: {
			teal: function () {
				return this.nb >= 7;
			},
			red: function () {
				return this.nb < 3;
			},
			pulse: function () {
				return this.nb > 7;
			}
		},
		props: {
			nb: {
				type: Number, // restriction sur m'héritage de propriétés 
			},
		},
	}

</script>
<style scoped>
	div p {
		margin-top: 0px;
	}
	
	.pulse {
		margin-top: 30px;
		margin-bottom: 30px;
	}
	
	.teal p {
		color: #fff;
	}
</style>