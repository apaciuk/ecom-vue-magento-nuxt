<template>
<header id="site-head">
			<div class="uk-container uk-container-expand">
				<div class="uk-grid uk-grid-medium uk-flex uk-flex-middle uk-flex-between" data-uk-grid>
					<div class="uk-width-auto" id="logo">
						<a href="#" class="uk-logo" title="eCommerce"><img src="logo.svg" alt="Logo"></a>
					</div>
                     <div class="uk-width-auto">
					    <ul class="uk-subnav" data-uk-margin>
                         <li class="uk-visible@s"><NuxtLink to="/">Home</NuxtLink></li>
						  	  <li class="uk-visible@s"><NuxtLink to="/">About</NuxtLink></li>
							<li class="uk-visible@s"><NuxtLink to="/contact">Collections</NuxtLink></li>
								  <li class="uk-visible@s"><NuxtLink to="/">Categories</NuxtLink></li>
							<li class="uk-visible@s"><NuxtLink to="/contact">Best Sellers</NuxtLink></li>
									  <li class="uk-visible@s"><NuxtLink to="/">Instagram</NuxtLink></li>
							<li class="uk-visible@s"><NuxtLink to="/contact">Trending</NuxtLink></li>
								  <li class="uk-visible@s"><NuxtLink to="/">Sale</NuxtLink></li>
							<li class="uk-visible@s"><NuxtLink to="/contact">New</NuxtLink></li>
								<li class="uk-visible@s"><NuxtLink to="/contact">Journal</NuxtLink></li>
							<li class="uk-visible@s"><NuxtLink to="/contact">Contact</NuxtLink></li>
                           <li class="uk-visible@s"> <VmSearch></VmSearch></li>
				            <li class="uk-visible@s">
								<a href="#" data-uk-icon="icon:cart"></a>
								<div class="drop-nav uk-dropdown" data-uk-dropdown="mode: click; offset: 20;animation: uk-animation-slide-bottom-small; duration: 150">
									<h4 class="uk-margin-small-bottom uk-margin-remove-adjacent">Shopping Cart</h4>
								    <hr>
                                     <ul class="uk-nav-default uk-nav-parent-icon" data-uk-nav>
									<li><img src="purse.jpg" width="60" /><span class="uk-margin-small-left"></span>Mens Purse £240<span class="uk-margin-small-left" data-uk-icon="icon: trash"></span><span class="uk-margin-small-left" data-uk-icon="icon: pencil"></span></li>
									</ul>
                                    <hr>
									<a href="#" class="uk-button uk-button-secondary uk-width-1-1">CHECKOUT</a>
									<hr>
									</div>
							     </li>
	                        	<li class="uk-visible@s">
								<a href="#" data-uk-icon="icon:user"></a>
								<div class="drop-nav uk-dropdown" data-uk-dropdown="mode: click; offset: 20;animation: uk-animation-slide-bottom-small; duration: 150">
									<h4 class="uk-margin-small-bottom uk-margin-remove-adjacent">Account</h4>
								    <hr>
                                    <ul v-if="isUserLoggedIn" class="uk-list uk-list-space">
									 <li><span class="uk-margin-small-right" data-uk-icon="icon: user"></span>Welcome {{ getUserName }}</li>
								   
									  <li><span class="uk-margin-small-right" data-uk-icon="icon: cog"></span>Account</li>
									   <li><span class="uk-margin-small-right" data-uk-icon="icon: mail"></span>Messsages</li>
									  <li ><a href="#" class="uk-button uk-button-secondary uk-width-1-1">Log Out</a></li>
									 </ul>
									  <ul v-else class="uk-list uk-list-space">
									  <li ><a href="#" class="uk-button uk-button-secondary uk-width-1-1">Sign Up</a></li>
                                     </ul>
									<hr>
								</div>
							</li>
							<li class="uk-visible@s">
								<a href="#" data-uk-icon="icon:heart"></a>
								<div class="drop-nav uk-dropdown" data-uk-dropdown="mode: click; offset: 20;animation: uk-animation-slide-bottom-small; duration: 150">
									<NuxtLink :to="{ name: 'user-wishlist' }"><h4 class="uk-margin-small-bottom uk-margin-remove-adjacent"></h4>
											{{ wishlistLabel }}
				                    </NuxtLink>
									<hr>
                                    <ul class="uk-nav-default uk-nav-parent-icon" data-uk-nav>
								
									<li><img src="purse.jpg" width="60" /><span class="uk-margin-small-left"></span>Mens Purse £240<span class="uk-margin-small-left" data-uk-icon="icon: trash"></span><span class="uk-margin-small-left" data-uk-icon="icon: pencil"></span></li>
									</ul>
                                    <hr>
									<a href="#" class="uk-button uk-button-secondary uk-width-1-1">ADD ALL TO CART</a>
									<hr>
									
								</div>
							</li>
						<li class="uk-hidden@s"><a data-uk-navbar-toggle-icon data-uk-toggle href="#offcanvas-nav"></a></li>
						</ul>
					</div>
				</div>
			</div>
                 <OffCanvas />
		</header>
   
     <!--/HEADER-->
</template>
<script>
import VmSearch from '../search/Search';
import OffCanvas from '@/components/header/OffCanvas';


export default {
name: 'Header',
 data () {
      return {
       isCheckoutActive: false,
       isMenuOpen: false
      }
    },
components: {
      VmSearch, 
      OffCanvas
},
  computed: {
      numProductsAdded () {
        return this.$store.getters.productsAdded.length;
      }
    },

    methods: {
      showCheckoutModal () {
        this.$store.commit('showCheckoutModal', true);
      }
   }
}
</script>

<style scoped>
#site-head {
padding-right: 50px;
padding-left: 30px;
}
#logo {
padding-bottom: 6px;
}
h4.uk-margin-small-bottom {
text-transform: uppercase;
font-size: 1em;
}
li.uk-visible@s a {
padding-right: 20px;
}
</style>
