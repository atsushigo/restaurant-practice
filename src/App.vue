<template>
	<div id="app">
		<NavBar />
		<RestaurantPics />
		<Menu />
		<Appointment />
		<Gallery />
		<Footer />
		<!-- <router-view /> -->
	</div>
</template>

<script type="text/javascript">
import NavBar from '@/components/NavBar.vue';
import RestaurantPics from '@/components/RestaurantPics.vue';
import Menu from '@/components/Menu.vue';
import Appointment from '@/components/Appointment.vue';
import Gallery from '@/components/Gallery.vue';
import Footer from '@/components/Footer.vue';
export default {
	name: 'App',
	components: { NavBar, RestaurantPics, Menu, Appointment, Gallery, Footer },
	data: () => ({})
};
</script>

<style>
html {
	scroll-behavior: smooth;
}

.navbar {
	position: fixed;
	top: 0;
	left: 0;
	width: 100%;
	z-index: 100;
}
.home-section {
	height: 500px;
	background-image: url("../public/images/restau-img-2.jpg");
	background-attachment: fixed;
	background-size: cover;
}
.our-menus {
	padding: 50px 0px;
	background-color: #fcf9f5;
}
.menu-categories > ul {
	font-size: 0;
	line-height: 0;
	text-align: center;
	margin-bottom: 70px;
}
.menu-categories > ul > li {
	display: inline-block;
	cursor: pointer;
	vertical-align: top;
	font-size: 18px;
	line-height: 26px;
	letter-spacing: 4px;
	font-weight: 700;
	text-transform: uppercase;
	margin: 0 22px;
	-webkit-transition: all 0.3s;
	transition: all 0.3s;
}
.menu-categories > ul > li.active {
	color: #ffc851;
}
.menu-tabs {
	display: none;
}
.active_menu_tab {
	display: block;
}
.menu_block_item {
	padding: 10px 5px;
}
.menu_block_item > .menu_img {
	padding: 0 35px;
	margin-bottom: 30px;
	text-align: center;
}
.menu_block_item > .menu_img > img {
	max-width: 100%;
	border-radius: 50%;
	width: 175px;
	height: 175px;
}
.menu_block_item > h5 {
	text-align: center;
	font-size: 20px;
	letter-spacing: 4px;
	font-weight: 700;
	text-transform: uppercase;
	font-family: 'PT Sans Narrow';
}
.menu_block_item > p {
	font-size: 14px;
	margin: 14px 0 18px 0;
	text-align: center;
}
.menu_block_item > .menu_price {
	font-size: 24px;
	line-height: 26px;
	letter-spacing: 3px;
	margin-bottom: 20px;
	text-align: center;
}
.menu_block_item:hover {
	cursor: pointer;
	box-shadow: 0 14px 28px rgba(0, 0, 0, 0.25), 0 10px 10px rgba(0, 0, 0, 0.22);
}
.menu_block_item:hover > h5 {
	color: #ffc851;
}
.book-appointment {
	padding: 50px 0px;
}
.book-appointment {
	background-image: url("../public/images/reservation-bg.jpg");
	background-position: center;
	background-size: cover;
}
.reservation-block {
	max-width: 700px;
	margin: auto;
	background: transparent;
}
#appointment-form input,
#appointment-form textarea {
	background: transparent;
	border: 2px solid;
	width: 100%;
	font-size: 14px;
	line-height: 26px;
	letter-spacing: 3px;
	vertical-align: top;
	padding: 5px 15px 7px;
	border-color: #000000;
	border-radius: 0;
	color: #ffffff;
	height: auto;
	-webkit-appearance: none;
}
#appointment-form .submit-bttn {
	display: block;
	margin: auto;
	width: 250px;
	color: #000000;
}
#appointment-form .submit-bttn:hover {
	background-color: #1d2326;
	color: white;
}
.image-gallery {
	padding: 100px 0px;
}
.image_gallery_item {
	position: relative;
}
.image_gallery_item > img {
	max-width: 100%;
}
.image-gallery .col-md-3 {
	padding: 30px;
}
.image_overlay {
	position: absolute;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
	z-index: 3;
	opacity: 0;
	-webkit-transition: all 0.3s;
	transition: all 0.3s;
	background-color: #ffc851;
}
.image_gallery_item:hover .image_overlay {
	opacity: 0.8;
	cursor: pointer;
}
.image_gallery_item:after {
	content: '+';
	width: 60px;
	height: 60px;
	background: #121618;
	border-radius: 50%;
	font-size: 32px;
	line-height: 55px;
	text-align: center;
	position: absolute;
	top: 50%;
	left: 50%;
	-webkit-transform: translateX(-50%) translateY(-50%) scale(0);
	transform: translateX(-50%) translateY(-50%) scale(0);
	-webkit-transition: all 0.3s;
	transition: all 0.3s;
	z-index: 7;
	color: white;
}
.image_gallery_item:hover:after {
	-webkit-transform: translateX(-50%) translateY(-50%) scale(1);
	transform: translateX(-50%) translateY(-50%) scale(1);
}
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
	background-color: rgba(0, 0, 0, 0.9); /* Black w/ opacity */
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

@keyframes zoom {
	from {
		transform: scale(0);
	}
	to {
		transform: scale(1);
	}
}
/* 100% Image Width on Smaller Screens */
@media only screen and (max-width: 700px) {
	.my-modal-content {
		width: 100%;
	}
}

.navbar-nav > li {
	margin: 0px 10px;
}

.nav-link:hover {
	color: #ffc851 !important;
}
.navbar-light .navbar-nav .active > .nav-link {
	color: #ffc851 !important;
}
.navbar-nav .nav-link {
	text-transform: uppercase;
}
.navbar-brand {
	font-family: 'PT Sans Narrow';
	font-size: 30px;
	font-weight: bold;
}
.navbar {
	box-shadow: 0 2px 4px 0 rgba(0, 0, 0, 0.2);
}
.section-header {
	text-align: center;
	margin-bottom: 40px;
}
.section-header > .section-tagline {
	color: #ffc851;
	font-size: 20px;
	font-weight: 400;
	font-family: 'PT Sans Narrow';
	margin-bottom: 10px;
}
.section-header > .section-title {
	font-size: 40px;
	line-height: 48px;
	font-weight: 400;
	letter-spacing: 0;
	font-family: 'PT Sans Narrow';
	margin-bottom: 10px;
	text-transform: uppercase;
}
.section-header > .separator {
	width: 150px;
	background: #ffc851;
}
#restau-pics-slider > .next-arr {
	color: #ffc851;
	border-color: #ffc851;
}
#restau-pics-slider > .next-arr:hover,
#restau-pics-slider > .next-arr:active {
	background-color: #ffc851;
	color: white;
}
#restau-pics-slider > .next-arr:focus {
	box-shadow: 0 0 0 0.2rem #ffc85178;
}

.activeImageGallery {
	display: block;
}
.footer {
	background-color: #121618;
	color: #ffc851;
	padding: 20px 0px;
	font-family: 'PT Sans Narrow';
}
.footer .social-net {
	list-style: none;
	margin: 0px;
	padding: 0px;
	float: right;
	display: inline;
}
.footer .social-net > li {
	display: inline;
	margin: 0 5px;
}
.footer .social-net > li > a {
	color: #ffc851;
}
.footer .social-net > li > a > i {
	color: #ffc851;
	font-size: 20px;
}
</style>
