<template>
	<div>
		<!-- Our Menus start -->
		<section class="our-menus" id="menus">
			<div class="container">
				<div class="section-header">
					<div class="section-tagline">Discover our Menu and taste the difference!</div>
					<div class="section-title">Our Menu</div>
					<hr class="separator" />
				</div>
				<div id="menus-picker">
					<div class="menu-categories">
						<ul>
							<li v-for="(menuCategory,i) in menuCategories" :key="i" v-bind:class="{ active: menuCategory == currentTab }" @click="toggleTab(menuCategory)">
								{{ menuCategory }}
							</li>
						</ul>
						<div id="burgers" class="menu-tabs" v-bind:class="{ active_menu_tab: 'Burgers' == currentTab }">
							<div class="row">
								<div class="col-md-3">
									<div class="menu_block_item">
										<div class="menu_img"><img :src='require("../../public/images/french-burger.jpeg")' alt="French Burger" /></div>
										<h5>French</h5>
										<p class="menu_description">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Optio enim, ratione hic doloremque</p>
										<div class="menu_price">$13</div>
									</div>
								</div>
								<div class="col-md-3">
									<div class="menu_block_item">
										<div class="menu_img"><img :src='require("../../public/images/vegetables-burger.jpeg")' alt="Vegetables Burger" /></div>
										<h5>Vegetables</h5>
										<p class="menu_description">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Optio enim, ratione hic doloremque</p>
										<div class="menu_price">$22</div>
									</div>
								</div>
								<div class="col-md-3">
									<div class="menu_block_item">
										<div class="menu_img"><img :src='require("../../public/images/vincent-burger.jpeg")' alt="Vincent Burger" /></div>
										<h5>Vincent</h5>
										<p class="menu_description">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Optio enim, ratione hic doloremque</p>
										<div class="menu_price">$13</div>
									</div>
								</div>
							</div>
						</div>
						<div id="desserts" class="menu-tabs" v-bind:class="{ active_menu_tab: 'Desserts' == currentTab }">
							<div class="row">
								<div class="col-md-3">
									<div class="menu_block_item">
										<div class="menu_img"><img :src='require("../../public/images/trilogie-de-verrines.jpg")' alt="Trilogie de Verrines" /></div>
										<h5>Trilogie de Verrines</h5>
										<p class="menu_description">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Optio enim, ratione hic doloremque</p>
										<div class="menu_price">$22</div>
									</div>
								</div>
								<div class="col-md-3">
									<div class="menu_block_item">
										<div class="menu_img"><img :src='require("../../public/images/classic-chocolate-mousse.jpg")' alt="Classic Chocolate Mousse" /></div>
										<h5>Classic Chocolate Mousse</h5>
										<p class="menu_description">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Optio enim, ratione hic doloremque</p>
										<div class="menu_price">$22</div>
									</div>
								</div>
							</div>
						</div>
						<div id="drinks" class="menu-tabs" v-bind:class="{ active_menu_tab: 'Drinks' == currentTab }"></div>
						<div id="pasta" class="menu-tabs" v-bind:class="{ active_menu_tab: 'Pasta' == currentTab }"></div>
						<div id="pizzas" class="menu-tabs" v-bind:class="{ active_menu_tab: 'Pizzas' == currentTab }">
							<div class="row">
								<div class="col-md-3">
									<div class="menu_block_item">
										<div class="menu_img"><img :src='require("../../public/images/diablo-pizza.png")' alt="Diablo Pizza" /></div>
										<h5>Diablo</h5>
										<p class="menu_description">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Optio enim, ratione hic doloremque</p>
										<div class="menu_price">$13</div>
									</div>
								</div>
								<div class="col-md-3">
									<div class="menu_block_item">
										<div class="menu_img"><img :src='require("../../public/images/carbonara-pizza.png")' alt="Carbonara Pizza" /></div>
										<h5>Carbonara</h5>
										<p class="menu_description">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Optio enim, ratione hic doloremque</p>
										<div class="menu_price">$15</div>
									</div>
								</div>
								<div class="col-md-3">
									<div class="menu_block_item">
										<div class="menu_img"><img :src='require("../../public/images/margherita-pizza.png")' alt="Margherita Pizza" /></div>
										<h5>Margherita</h5>
										<p class="menu_description">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Optio enim, ratione hic doloremque</p>
										<div class="menu_price">$21</div>
									</div>
								</div>
								<div class="col-md-3">
									<div class="menu_block_item">
										<div class="menu_img"><img :src='require("../../public/images/prosciutto-pizza.png")' alt="Prosciutto Pizza" /></div>
										<h5>Prosciutto</h5>
										<p class="menu_description">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Optio enim, ratione hic doloremque</p>
										<div class="menu_price">$17</div>
									</div>
								</div>
								<div class="col-md-3">
									<div class="menu_block_item">
										<div class="menu_img"><img :src='require("../../public/images/vincent-pizza.png")' alt="Vincent Pizza" /></div>
										<h5>Vincent</h5>
										<p class="menu_description">Lorem ipsum, dolor sit amet consectetur adipisicing elit. Optio enim, ratione hic doloremque</p>
										<div class="menu_price">$17</div>
									</div>
								</div>
							</div>
						</div>
						<div id="salads" class="menu-tabs" v-bind:class="{ active_menu_tab: 'Salads' == currentTab }"></div>
					</div>
				</div>
			</div>
		</section>
		<!-- Our Menus end -->
	</div>
</template>

<script>
export default {
	name: 'Menu',
	data() {
		return { menuCategories: ['Burgers', 'Desserts', 'Drinks', 'Pasta', 'Pizzas', 'Salads'], currentTab: 'Pizzas' };
	},
	methods: {
		toggleTab: function(clickedMenu) {
			this.currentTab = clickedMenu;
		}
	}
};
</script>

<style scoped></style>
