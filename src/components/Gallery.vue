<template>
	<div>
		<!-- Image Gallery Start -->
		<section class="image-gallery" id="gallery">
			<div class="container">
				<div class="section-header">
					<div class="section-title">Image Gallery</div>
					<hr class="separator" />
				</div>
				<div class="row">
					<div class="col-md-3" v-for="(galleryImage, i) in galleryImages" :key="i">
						<div class="image_gallery_item" :class='{"activeImageGallery":galleryImage.show}'  @click="enLargeImage(galleryImage)">
							<img :src="galleryImage.modal" alt="" />
							<div class="image_overlay"></div>
						</div>
						<!-- The Modal -->

						<div :id="i" class="my-modal" @click="closeModal(galleryImage)"><img class="my-modal-content" :src="galleryImage" /></div>
					</div>
				</div>
			</div>
		</section>
		<!-- Image Gallery End -->
	</div>
</template>

<script>
export default {
	name: 'Gallery',
	data() {
		return {
			galleryImages: [
				{ modal: require('../../public/images/gal_1.jpg'), show: true },
				{ modal: require('../../public/images/gal_2.jpg'), show: false },
				{ modal: require('../../public/images/gal_3.jpg'), show: false },
				{ modal: require('../../public/images/gal_4.jpg'), show: false },
				{ modal: require('../../public/images/gal_5.jpg'), show: false },
				{ modal: require('../../public/images/gal_6.jpg'), show: false },
				{ modal: require('../../public/images/gal_7.jpg'), show: false }
			]
		};
	},
	methods: {
		/* enLargeImage: function(imageID) {
			var element = document.getElementById(imageID);
			element.classList.add('activeImageGallery');
		},
		closeModal: function(imageID) {
			var element = document.getElementById(imageID);
			element.classList.remove('activeImageGallery');
		}, */

		enLargeImage: function(galleryImage) {
			galleryImage.show = true;
		},
		closeModal: function(galleryImage) {
			galleryImage.show = false;
		}
	}
};
</script>

<style scoped>
	/* The Modal (background) */
	.my-modal {
	display: none; /*Hidden by default */
	
	position: fixed; /* Stay in place */
	z-index: 100; /* Sit on top */
	padding: 50px 0px; /* Location of the box */
	left: 0;
	top: 0;
	width: 100%; /* Full width */
	height: 100%; /* Full height */
	background-color: rgba(0,0,0,0.9); /* Black w/ opacity */
	}
	
	/* Modal Content (Image) */
	.my-modal-content {
	margin: auto;
	display: block;
	max-width: 500px;
	}
	
	.my-modal-content {
	animation-name: zoom;
	animation-duration: 0.6s;
	}
</style>
