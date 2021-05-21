<template>
	<div class="home">
		<div class="title">Best Properties For Sale</div>
		<br />
		<p class="description">Lorem ipsum dolor sit amet, consec tetur cing elit. Suspe ndisse suscipit</p>

		<br />
		<div class="row" style="margin: 0 -20px">
			<div class="col-md-4" v-for="n in 3" :key="n" style="padding: 20px">
				<q-card flat bordered>
					<img src="https://cdn.quasar.dev/img/mountains.jpg" height="200" />
					<div class="property-statuses">
						<div class="property-status orange">Featured</div>
						<div class="property-status blue">For Sale</div>
					</div>

					<q-card-section>
						<div class="property-title">Villa on Hollywood Boulevard</div>
						<div class="property-description">1421 San Pedro St, Los Angeles</div>

						<div class="property-stats">
							<div class="property-stat">
								<q-icon name="mdi-sofa-outline" />
								<div>3 Br</div>
							</div>
							<div class="property-stat">
								<q-icon name="mdi-shower-head" />
								<div>3 Ba</div>
							</div>
							<div class="property-stat">
								<q-icon name="mdi-ruler-square" />
								<div>2300 Sq.Ft</div>
							</div>
							<div class="property-stat">
								<q-icon name="mdi-garage-variant" />
								<div>1 Gr</div>
							</div>
						</div>
					</q-card-section>

					<q-separator />

					<q-card-section>
						<div class="property-actions">
							<div class="property-price">$1.250.000</div>

							<div class="flex" style="column-gap: 15px">
								<q-btn outline round color="white" class="text-grey" style="font-size: 10px; padding: 5px" icon="mdi-heart-outline" />
								<q-btn outline round color="white" class="text-grey" style="font-size: 10px; padding: 5px" icon="sync_alt" />
							</div>
						</div>
					</q-card-section>
				</q-card>
			</div>
		</div>
	</div>
</template>


<style scoped lang="scss">
.home {
	background-color: white;
	padding: 20px 50px;
}

.title {
	position: relative;
	font-size: 32px;
	padding-bottom: 15px;
	font-weight: 500;
	color: #333;

	&::after {
		content: '';
		position: absolute;
		left: 0;
		bottom: 0;
		height: 2.5px;
		width: 70px;
		background-color: #0ec6d5;
	}
}

.description {
	color: #696969;
}

.q-card__section {
	color: #9b9b9b;
	font-weight: 500;
}

.property {
	&-statuses {
		display: flex;
		column-gap: 10px;
		position: absolute;
		left: 10px;
		top: 10px;
	}

	&-status {
		padding: 3px 8px;
		padding-bottom: 4px;
		color: white;
		letter-spacing: 1px;
		text-transform: uppercase;
		font-weight: 500;
		border-radius: 4px;

		&.orange {
			background-color: #ff6935;
		}

		&.blue {
			background-color: #0ec6d5;
		}
	}

	&-title {
		font-size: 17px;
		color: #252525;
		cursor: pointer;
		transition: 0.2s;
	}

	&-title:hover {
		color: #0ec6d5;
	}

	&-description {
		margin-top: 8px;
	}

	&-stats {
		display: flex;
		column-gap: 15px;
		margin-top: 15px;
	}

	&-stat {
		display: flex;
		column-gap: 3px;
		font-weight: 400;

		.q-icon {
			color: #0ec6d5;
			font-size: 22px;
		}
	}

	&-price {
		font-weight: 700;
		font-size: 17px;
		color: #333;
	}

	&-actions {
		display: flex;
		justify-content: space-between;
	}
}
</style>