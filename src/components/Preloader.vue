<!--Pour le preloader on peut utiliser avec VueResource : Before et après Then-->
<template>
	<div>
		<div class="preloader-wrapper small active">
			<div class="spinner-layer spinner-green-only">
				<div class="circle-clipper left">
					<div class="circle"></div>
				</div>
				<div class="gap-patch">
					<div class="circle"></div>
				</div>
				<div class="circle-clipper right">
					<div class="circle"></div>
				</div>
			</div>
		</div>
	</div>
</template>
<script>
	export default {
		name: 'preloader',
		props: ['perso'],
	}

</script>
<style scoped>

</style>