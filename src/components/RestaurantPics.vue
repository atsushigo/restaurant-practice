<template>
	<div>
		<!-- Our Restaurant Pics Start -->
		<section class="restau-pics" id="restau-pics" style="padding: 50px 0px;border-bottom: 2px solid #eee;overflow: hidden;">
			<div class="container">
				<div class="section-header">
					<div class="section-tagline">We are not the First but we are the BEST</div>
					<div class="section-title">Our Restaurants</div>
					<hr class="separator" />
				</div>
				<div id="restau-pics-slider" style="position: relative;">
					<button @click.prevent="previous()" class="btn btn-outline-secondary" type="button" style="border-radius: 0px;">
						<i class="fas fa-angle-double-left"></i>
					</button>
					<div id="ul-slider" style="overflow: hidden;margin: 10px 0px;" class="shadow-lg">
						<ul style="list-style: none; display: flex;padding: 0px;margin: 0px;">
							<li v-for="(image,i) in images" :key="i">
								<div><img v-bind:src="image" :alt="image" style="width: 350px;" /></div>
							</li>
						</ul>
					</div>
					<button @click.prevent="next()" type="button" class="btn btn-outline-primary next-arr" style="float: right;border-radius: 0px;">
						<i class="fas fa-angle-double-right"></i>
					</button>
				</div>
			</div>
		</section>
		<!-- Our Restaurant Pics End -->
	</div>
</template>

<script>
export default {
	name: 'RestaurantPics',
	data() {
		return {
			images: [
				require('../../public/images/restau-img-1.jpg'),
				require('../../public/images/restau-img-2.jpg'),
				require('../../public/images/restau-img-3.jpg'),
				require('../../public/images/restau-img-4.jpeg'),
				require('../../public/images/restau-img-5.jpg')
			]
		};
	},
	methods: {
		previous: function() {
			let el = document.getElementById('ul-slider');
			el.scrollLeft -= 50;
		},
		next: function() {
			let el = document.getElementById('ul-slider');
			el.scrollLeft += 50;
		}
	}
};
</script>

<style scoped></style>
