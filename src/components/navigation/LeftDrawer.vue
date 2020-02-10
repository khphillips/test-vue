<template>
	<div>
		<v-navigation-drawer v-model="drawer" :clipped="true" disable-route-watcher left app hide-overlay :mini-variant.sync="mini" :permanent="!$vuetify.breakpoint.xs" @input="updateValue()">
			<v-btn v-if="this.$vuetify.breakpoint.xs" small fab @click="close">
				<v-icon>fas fa-times</v-icon>
			</v-btn>
			<v-list dense>
				<menu-item icon="fas fa-home" route="Dashboard">Dashboard</menu-item>
				<menu-item icon="fas fa-adjust" route="About">About</menu-item>
				<menu-item icon="fas fa-archive" route="Page">Page</menu-item>
				<menu-item icon="fas fa-tools" :click="toggleUtilityDrawer">Utility Drawer</menu-item>
			</v-list>
		</v-navigation-drawer>
		<v-navigation-drawer v-model="utilDrawer" fixed temporary>Maybe some other tools</v-navigation-drawer>
	</div>
</template>
<script>
import MenuItem from './MenuItem.vue'
export default {
	props: ['value'],
	data: function() {
		return {
			drawer: !this.$vuetify.breakpoint.xs,
			utilDrawer: false,
		}
	},
	mounted: function() {
		this.drawer = !this.$vuetify.breakpoint.xs;
	},
	methods: {
		updateValue() {
			this.$emit('input', this.drawer)
		},
		toggleUtilityDrawer() {
			this.utilDrawer = !this.utilDrawer
		},
		close() {
			this.drawer = false;
			this.updateValue();
		}
	},
	watch: {
		'value': function(newV) {
			this.drawer = newV
		},
	},
	computed: {
		'mini': function() {
			if (this.$vuetify.breakpoint.xs) {
				return false;
			}
			return this.drawer;
		}
	},
	components: {
		MenuItem
	}
}
</script>