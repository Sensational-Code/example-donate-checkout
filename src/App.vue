
<template>
	<div class="inner">

		<!-- Charity info card -->
		<div class="inner__item">
			<CharityInfoCard />
		</div>

		<!-- Payment card -->
		<div class="inner__item">
			<PaymentCard />
		</div>

		<!-- Footer -->
		<div class="inner__item">
			<Footer />
		</div>

	</div>
</template>

<script>

	import CharityInfoCard from './components/CharityInfoCard.vue';
	import PaymentCard from './components/PaymentCard.vue';
	import Footer from './components/Footer.vue';

	export default {
		components: {
			CharityInfoCard,
			PaymentCard,
			Footer
		}
	}

</script>

<style scoped>
		
	/* Grid layout */
	.inner {
		display: grid;
		grid-template-columns: 55% 45%;
		justify-content: center;
		align-content: center;
		max-width: 900px;
	}

	@media (max-width: 900px) {
		.inner {
			grid-template-columns: 1fr;
		}
	}

	.inner__item {
		display: flex;
		justify-content: center;
	}

</style>
