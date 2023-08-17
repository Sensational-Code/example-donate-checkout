<template>

	<!-- Payment card -->
	<div class="payment-card">

		<!-- Header text -->
		<h3 class="payment-card__header">Choose amount to give</h3>
				
		<!-- Payment type (once/recurring) -->
		<div class="row payment-card__type">
			<button class="button col" :class="{ 'button--primary': paymentType === 'once' }" @click="setPaymentOnce">Give once</button>
			<button class="button col" :class="{ 'button--primary': paymentType === 'recurring' }" @click="setPaymentRecurring">Recurring</button>
		</div>

		<!-- Currency input -->
		<input v-model="inputAmount" type="number" class="payment-card__input" @input="handleAmountInput">
		<div class="payment-card__subtext">$250 gives 2 girls food for 1 year.</div>

		<!-- Quick select payment amounts -->
		<div class="payment-card__amounts">

			<!-- This is a little ugly and would be easier with css grid, but this flex method
					 has the benefit of accomdating an odd number of amounts and keeping them centered.
					 If we know for sure that there are only an even number of buttons, then this can
					 all be one clean loop rather than using math to split them into rows -->

			<!-- First row of buttons -->
			<div class="row">
				<button
					v-for="amount in quickSelectAmounts.slice(0, Math.min(quickSelectAmounts.length/2))"
					class="button col"
					:class="{ 'button--primary': amount == inputAmount }"
					@click="handleQuickAmount(amount)"
				>
					{{ currencySymbol }}{{ amount }}
				</button>
			</div>

			<!-- Second row of buttons -->
			<div class="row">
				<button
					v-for="amount in quickSelectAmounts.slice(Math.min(quickSelectAmounts.length/2), quickSelectAmounts.length)"
					class="button col"
					:class="{ 'button--primary': amount == inputAmount }"
					@click="handleQuickAmount(amount)"
				>
					{{ currencySymbol }}{{ amount }}
				</button>
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
</template>

<script>

	export default {
		data() {
			return {
				paymentType: 'once',
				inputAmount: '250',
				currency: 'USD',
				currencySymbol: '$',

				// Get from API or SSR injection in real-life scenario
				quickSelectAmounts: [
					'10',
					'100',
					'200',
					'500',
					'750',
					'1000'
				]
			}
		},

		methods: {
			setPaymentOnce() {
				this.paymentType = 'once';
			},

			setPaymentRecurring() {
				this.paymentType = 'recurring';
			},

			handleAmountInput(event) {},

			handleQuickAmount(amount) {
				this.inputAmount = `${amount}`;
			},

			handleNext() {
				console.log('next');
			}
		}
	}

</script>

<style scoped>
	
	/* Payment card */
	.payment-card {
		max-width: 500px;
		border-radius: 20px;
		overflow: hidden;
		box-shadow: var(--default-shadow);
		padding: 24px;
		/*margin: 15px;*/
		margin: 8px;
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
		color: var(--blue);
		/*font-size: 32px;*/
    font-size: 2rem;
    line-height: 1.25;
    height: 72px;
    padding-left: 16px;
    font-weight: 700;
		margin-bottom: 9px;
		width: 100%;
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

</style>
