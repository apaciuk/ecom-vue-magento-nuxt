<template>
  		<form class="uk-search uk-search-default">
                <span class="uk-search-icon-flip" uk-search-icon></span>
                <input class="uk-search-input" 
				 type="search" 
				 placeholder="Search items"
				 v-model="value"
				 @keyup="search(value)">
            </form>
		
</template>

<script>
export default {
  name: 'search',
	data () {
		return {
			value: ''
		}
	},

	computed: {
		placeholder () {
			if (this.$route.path === '/wishlist') {
				return 'Search in wishlist...';
			} else {
				return 'Search...';
			}
		}
	},

	methods: {
		search (value) {
			if (value.length > 0) {
				this.$store.commit('setHasUserSearched', true);
				this.$store.commit('setProductTitleSearched', value);
			} else {
				this.$store.commit('setHasUserSearched', false);
				this.$store.commit('setProductTitleSearched', '');
			}
		}
	}
}
</script>

