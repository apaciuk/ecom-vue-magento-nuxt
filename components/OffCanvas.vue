<template>
 <!-- OFFCANVAS -->
		<div id="offcanvas-nav" data-uk-offcanvas="flip: true; overlay: true">
			<div class="uk-offcanvas-bar uk-offcanvas-bar-animation uk-offcanvas-slide">
				<button class="uk-offcanvas-close uk-close uk-icon" type="button" data-uk-close></button>
			    <ul class="uk-nav uk-nav-offcanvas uk-nav-parent-icon" data-uk-nav="{ multiple: true }">
					<li class="uk-nav-header">Menu</li>
					<li><a href="#js-options"><span class="uk-margin-small-right uk-icon" data-uk-icon="icon: thumbnails"></span> Item</a></li>
			   </ul>
				<h4>Information</h4>
				<p>eCommerce using UIKit 3, Nuxt Js and Vue JS, with Off Canvas and other UIKit components.</p>
				<Search />
                		<h4>Cart</h4>
                        <ul class="uk-nav uk-nav-offcanvas uk-nav-parent-icon" data-uk-nav="{ multiple: true }">
								
						<li><img src="purse.jpg" width="60" /><span class="uk-margin-small-left"></span>Mens Purse £240<span class="uk-margin-small-left" data-uk-icon="icon: trash"></span><span class="uk-margin-small-left" data-uk-icon="icon: pencil"></span></li>
						</ul>
                        <hr>
						<a href="#" class="uk-button uk-button-secondary uk-width-1-1">CHECKOUT</a>
				 <ul v-if="isUserLoggedIn" class="uk-nav uk-nav-offcanvas uk-nav-parent-icon" data-uk-nav="{ multiple: true }">
			     <li><span class="uk-margin-small-right" data-uk-icon="icon: user"></span>Welcome{{ getUserName }}</li>
				 </ul>
				 <ul v-else class="uk-nav uk-nav-offcanvas uk-nav-parent-icon" data-uk-nav="{ multiple: true }">
				 <NuxtLink to="/login" id="login" class="uk-button uk-button-primary uk-border-rounded uk-align-center">Login</NuxtLink>
				  <hr>
			    <NuxtLink to="/login" id="login" class="uk-button uk-button-primary uk-border-rounded uk-align-center">Sign Up</NuxtLink>
				</ul>
			</div>
		</div>
		<!-- /OFFCANVAS -->
</template>
<script>
export default {
name: 'OffCanvas',    
}
</script>

<style scoped>
</style>
