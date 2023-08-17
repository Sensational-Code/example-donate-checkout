<template>
	<div class="footer">

		<!-- Merchant info -->
		<div class="footer__section">
			<div class="footer__text">Merchant Legal Name or DBA</div>
			<div class="footer__text">Address 1</div>
			<div class="footer__text">City, State, Zip</div>
		</div>

		<!-- Donor support info -->
		<div class="footer__section">
			<div class="footer__text">Donor Support</div>
			<div class="footer__text">email@merchant.com</div>
			<div class="footer__text">or (123)-456-9870</div>
		</div>

		<!-- Links -->
		<div class="footer__section">
			<a href="#" class="footer__text link d-block">Refund Policy</a>
			<a href="#" class="footer__text link d-block">Privacy Policy</a>
			<a href="#" class="footer__text link d-block">Terms & Conditions</a>
		</div>

	</div>
</template>

<script>

	export default {

	}

</script>

<style scoped>

	/* Footer */
	.footer {
		max-width: 500px;
		display: flex;
		justify-content: space-between;
		flex-wrap: wrap;
		padding: 24px
	}

	.footer__section {
		margin: 10px;
		font-size: 0.8rem;
	}

	.footer__text {
		color: rgb(90, 120, 140);
		/*font-size: 14px;*/
		font-size: 0.9rem;
		font-weight: 500;
	}

</style>