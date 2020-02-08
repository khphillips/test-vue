<template>
	<div>
		<v-navigation-drawer v-model="drawer" right app clipped @input="updateValue()">
			<v-list dense>
				<menu-item icon="fas fa-building">Some Where</menu-item>
			</v-list>
		</v-navigation-drawer>
		<v-navigation-drawer right v-model="utilDrawer" fixed temporary />
	</div>
</template>
<script>
import MenuItem from './MenuItem.vue'

export default {
	props: ['value'],
	data: () => ({
		drawer: false,
		utilDrawer: false
	}),
	methods: {
		updateValue() {
			console.log('update')
			this.$emit('input', this.drawer)
		}
	},
	watch: {
		'value': function(newV) {
			console.log(newV)
			this.drawer = newV
		},
	},
	components: {
		MenuItem
	}
}
</script>