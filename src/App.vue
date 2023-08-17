
<template>
	<div class="inner">

		<div class="inner__item">
			<!-- Card -->
			<div class="card">

				<!-- Card image -->
	  		<img class="card__image" src="./assets/images/pattern.png" alt="card image">
				
				<!-- Card content -->
				<div class=card__inner>
					<img class="card__profile-image" src="./assets/images/profile-pattern.png" alt="card image">
					<h3>Doing Orphan Care Differently.</h3>
					<p>Child Hope International is a 501c3 organization
							ministering to orphans and widows in their distress by
							transitioning children from orphanages into loving
							families. We do this through Christ-centered care
							training, and social work.
					</p>

					<!-- Card footer -->
					<div class="card__footer">
						<a href="#" class="link">Planned Giving</a>
						<a href="#" class="link">Donate Stock</a>
						<a href="#" class="link">Donate Crypto</a>
					</div>
				</div>
			</div>
		</div>


		<div class="inner__item">
			<!-- Payment box -->
			<div class="payment-card">

				<!-- Header text -->
				<h3 class="payment-card__header">Choose amount to give</h3>
						
				<!-- Payment type (once/recurring) -->
				<div class="row payment-card__type">
					<button class="button col" :class="{ 'button--primary': paymentType === 'once' }" @click="setPaymentOnce">Give once</button>
					<button class="button col" :class="{ 'button--primary': paymentType === 'recurring' }" @click="setPaymentRecurring">Recurring</button>
				</div>

				<!-- Currency input -->
				<input v-model="inputAmount" @input="handleAmountInput" class="payment-card__input">
				<div class="payment-card__subtext">$250 gives 2 girls food for 1 year.</div>

				<!-- Quick select payment amounts -->
				<div class="payment-card__amounts">
					<div class="row">
						<button class="button col">$10</button>
						<button class="button col">$100</button>
						<button class="button col">$200</button>
					</div>
					<div class="row">
						<button class="button col">$500</button>
						<button class="button col">$750</button>
						<button class="button col">$1000</button>
					</div>
				</div>

				<!-- Footer -->
				<div class="payment-card__footer">

					<!-- Designation -->
					<div class="payment-card__designation">Designation: General Support</div>

					<!-- Option to give in memory of -->
					<div class="payment-card__memory">
						<input type="checkbox">
						<label>Give in honor or memory of someone</label>
					</div>

					<!-- Next step button -->
					<button class="button button--primary w-100" @click="handleNext">Next</button>
				</div>
			</div>
		</div>


		<!-- Footer -->
		<div class="inner__item footer">

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

	</div>
</template>

<script>

	export default {
		data() {
			return {
				paymentType: 'once',
				inputAmount: '250',
				currency: 'USD',
				currencySymbol: '$'
			}
		},

		methods: {
			setPaymentOnce() {
				this.paymentType = 'once';
			},

			setPaymentRecurring() {
				this.paymentType = 'recurring';
			},

			handleAmountInput() {},

			handleNext() {
				console.log('next');
			}
		}
	}

</script>

<style scoped>
		
	/* Grid layout */
	.inner {
		/*display: flex;
		flex-wrap: wrap;*/
		display: grid;
	  grid-template-columns: 55% 45%;
	  gap: 16px;
	  padding: 10px;
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


		/* Links */
	.link {
		/*font-size: 18px;*/
    font-size: 1.1rem;
    font-weight: 700;
    line-height: 1.1;
    color: var(--link-primary);
	}


	/* Helper classes */
	.w-100 {
		width: 100%;
	}

	.d-block {
		display: block;
	}

	.row {
		display: flex;
	}

	.col {
		flex-grow: 1;
		flex-basis: 0;
	}


	/* Inputs */
	input[type="checkbox"] {
		border: 8px solid gray;
		border-radius: 4px;
		width: 20px;
		height: 20px;
	}

	input {
		/*height: 60px;*/
		border: 2px solid rgb(95, 112, 186);
		border-radius: 8px;
	}

	input:focus {
		outline: 3px solid rgba(143.65, 155.48, 206.98, 0.3);
	}


	/* Card */
	.card {
		max-width: 500px;
		border-radius: var(--border-radius);
		overflow: hidden;
		box-shadow: 15px 15px 42px 0px #EBEBEB;
		/*margin: 15px;*/
	}

	.card__image {
		width: 100%;
	}

	.card__profile-image {
		width: 72px;
		height: 72px;
		border-radius: 100%;
		margin-top: -40px;
	}

	.card__inner {
		padding-bottom: 24px;
		padding-left: 24px;
		padding-right: 24px;
	}

	.card__inner h3 {
		font-weight: 700;
		/*font-size: 32px;*/
		font-size: 2rem;
		margin-top: 17px;
		margin-bottom: 10px;
		line-height: 1.25;
		/*color: var(--text-primary);*/
	}

	.card__inner p {
		line-height: 1.33;
		font-weight: 400;
		/*font-size: 18px;*/
		font-size: 1.1rem;
		/*color: var(--text-primary);*/
	}

	.card__footer {
		display: flex;
		/*justify-content: flex-end;*/
		justify-content: space-around;
		margin-top: 90px;
		/*margin-right: 8px;*/
	}


	/* Payment card */
	.payment-card {
		max-width: 500px;
		border-radius: 20px;
		overflow: hidden;
		box-shadow: 15px 15px 42px 0px #EBEBEB;
		padding: 24px;
		/*margin: 15px;*/
		display: flex;
		flex-direction: column;
		flex-grow: 1;
		background-color: white;
	}

	.payment-card__header {
		font-size: 1.4rem;
		font-weight: 700;
		margin-top: 8px;
		margin-bottom: 35px;
		line-height: 1.4;
		display: flex;
		justify-content: center;
		margin-bottom: 30px;
	}

	.payment-card__type {
		margin-bottom: 24px;
	}

	.payment-card__input {
		color: rgb(95, 112, 186);
		/*font-size: 32px;*/
    font-size: 2rem;
    line-height: 1.25;
    height: 72px;
    /*padding: 19px;*/
    padding-left: 16px;
    font-weight: 700;
		margin-bottom: 9px;
	}

	.payment-card__subtext {
		font-size: 14px;
		font-size: 0.9rem;
		font-weight: 400;
		margin-bottom: 10px;
	}

	.payment-card__amounts .button {
		margin: 4px;
	}

	.payment-card__footer {
		margin-top: auto;
	}

	.payment-card__designation {
		/*font-size: 16px;*/
		font-size: 1rem;
		margin-bottom: 18px;
		margin-top: 70px;
	}

	.payment-card__memory {
		display: flex;
		align-items: center;
		/*font-size: 16px;*/
		font-size: 1rem;
		margin-bottom: 35px;
	}

	.payment-card__memory label {
		margin-left: 8px;
	}

	/* Buttons */
	.button {
		background-color: var(--button-color);
		color: var(--text-gray);
		/*height: 40px;*/
		/*font-size: 18px;*/
		font-size: 1.1rem;
		font-weight: 700;
		outline: none;
		border: none;
		border-radius: 8px;
		padding: 15px;
		/*height: 48px;*/
		border: 2px solid rgb(238, 238, 238);
		box-shadow: 0px 1px 2px rgba(16,24,40, 0.05);
	}

	.button:hover {
		background-color: rgb(212.5, 221, 233.75);
	}

	.button:active {
		outline: 2px solid rgb(212.5, 221, 233.75);
	}

	.button--selected {
		background-color: rgb(212.5, 221, 233.75);
	}

	.button--primary {
		background-color: rgb(95, 112, 186);
		color: white;
		border: none;
		outline: none;
	}

	.button--primary:hover {
		background-color: rgb(67.227, 83.791, 155.9);
		color: white;
	}

	.button--primary:active {
		outline: 2px solid rgba(143.65, 155.48, 206.98, 0.5);
	}


	/* Footer */
	.footer {
		max-width: 500px;
		display: flex;
		justify-content: space-between;
		flex-wrap: wrap;
		padding-left: 25px;
		padding-right: 25px;
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
