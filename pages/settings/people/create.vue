<template>
</template>

<script>
	export default {
		layout: function(context) {
			return 'settings/people/create';
		},

		asyncData({ store }) {
			store.state.mode = 'people-create';
			store.state.pageName = 'settings people-create';
		},

		data: function() {
			return {
				authenticated: this.$store.state.user != undefined
			}
		},

    middleware: function({ store, redirect }) {
		  if (store.state.user == undefined) {
		    return redirect('/');
      }
    }
	}
</script>
