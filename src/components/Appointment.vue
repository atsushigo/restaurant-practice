<template>
	<div>
		<!-- Book Appointment Start-->
		<section class="book-appointment" id="reservation">
			<div class="container">
				<div class="section-header">
					<div class="section-tagline" style="color: white;">You have a special event? we are here for you!</div>
					<div class="section-title">Make a Reservation</div>
					<hr class="separator" style="background-color: white;" />
				</div>
				<div class="reservation-block">
					<div class="form-block">
						<form action="" id="appointment-form" @submit="checkForm" method="POST">
							<div class="row">
								<div class="col-md-4">
									<div class="form-group">
										<label for="fullname">Full Name</label>
										<input type="text" class="form-control" v-model="full_name" />
										<div class="invalid-feedback" style="display: block;" v-if="full_name === null">Full name required</div>
									</div>
								</div>
								<div class="col-md-4">
									<div class="form-group">
										<label for="email">Email address</label>
										<input type="text" class="form-control" v-model="email" />
										<small class="form-text text-muted" style="color: #ffffff !important;">We'll never share your email with anyone else.</small>
										<div class="invalid-feedback" style="display: block;" v-if="email === null">Valid email required</div>
									</div>
								</div>
								<div class="col-md-4">
									<div class="form-group">
										<label for="phone">Phone</label>
										<input type="tel" class="form-control" pattern="[0-9]{3}-[0-9]{2}-[0-9]{3}" v-model="phone" />
										<small class="form-text text-muted" style="color: #ffffff !important;">Format: 123-45-678</small>
										<div class="invalid-feedback" style="display: block;" v-if="phone === null">Phone is required</div>
									</div>
								</div>
							</div>

							<div class="row">
								<div class="col-md-6">
									<div class="form-group">
										<label for="date">Date</label>
										<input type="date" class="form-control" v-model="date" min="" />
										<div class="invalid-feedback" style="display: block;" v-if="date === null">Date is required</div>
									</div>
								</div>
								<div class="col-md-6">
									<div class="form-group">
										<label for="time">Time</label>
										<input type="time" class="form-control" v-model="time" />
										<div class="invalid-feedback" style="display: block;" v-if="time === null">Time is required</div>
									</div>
								</div>
							</div>
							<div class="form-group">
								<label for="message">Message</label>
								<textarea class="form-control" v-model="message" style="resize: none;"></textarea>
								<div class="invalid-feedback" style="display: block;" v-if="message === null">Message is required</div>
							</div>
							<p><input type="submit" value="Book a table" class="submit-bttn" /></p>
						</form>
					</div>
				</div>
			</div>
		</section>
		<!-- Book Appointment End-->
	</div>
</template>

<script>
export default {
	name: 'RestaurantPics',
	data() {
		return {
			errors: [],
			full_name: '',
			email: '',
			phone: '',
			date: '',
			time: '',
			message: ''
		};
	},
	methods: {
		checkForm: function(event) {
			if (this.full_name && this.validEmail(this.email) && this.phone && this.date && this.message && this.time) {
				return true;
			}

			this.errors = [];

			if (!this.full_name) {
				this.errors.push('Full name is required');
				this.full_name = null;
			}

			if (!this.validEmail(this.email)) {
				this.errors.push('Valid email required.');
				this.email = null;
			}

			if (!this.phone) {
				this.errors.push('Phone is required');
				this.phone = null;
			}

			if (!this.date) {
				this.errors.push('Date is required');
				this.date = null;
			}

			if (!this.time) {
				this.errors.push('Time is required');
				this.time = null;
			}

			if (!this.message) {
				this.errors.push('Message is required');
				this.message = null;
			}

			event.preventDefault();
		},
		validEmail: function(email) {
			var re = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/;
			return re.test(email);
		}
	}
};
</script>

<style scoped></style>
