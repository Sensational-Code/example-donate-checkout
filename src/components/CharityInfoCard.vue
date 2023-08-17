
<template>

	<!-- Card -->
	<div class="card">

		<!-- Card image -->
		<img class="card__image" src="@/assets/images/pattern.png" alt="card image">
		
		<!-- Card content -->
		<div class="card__inner">
			<img class="card__profile-image" src="@/assets/images/profile-pattern.png" alt="card image">
			<h3>Doing Orphan Care Differently.</h3>
			<p>Child Hope International is a 501c3 organization
					ministering to orphans and widows in their distress by
					transitioning children from orphanages into loving
					families. We do this through Christ-centered care,
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
</template>

<script>

	export default {

	}

</script>

<style scoped>

	/* Card */
	.card {
		max-width: 500px;
		border-radius: var(--border-radius);
		overflow: hidden;
		box-shadow: var(--default-shadow);
		margin: 8px;
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
	}

	.card__inner p {
		line-height: 1.33;
		font-weight: 400;
		/*font-size: 18px;*/
		font-size: 1.1rem;
	}

	.card__footer {
		display: flex;
		justify-content: space-around;
		margin-top: 90px;
	}

</style>
