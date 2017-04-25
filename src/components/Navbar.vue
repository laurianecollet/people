<template>
	<div>
		<nav>
			<div class="nav-wrapper">
				<h2>{{title}}</h2>
			</div>
		</nav>
	</div>
</template>
<script>
	export default {
		name: 'navbar',
		props: {
			title: {
				type: String, // restriction sur m'héritage de propriétés 
			}
		}
	}

</script>
<style scoped>
	h2 {
		margin: 0px;
	}
</style>