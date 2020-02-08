<template>
	<v-list-item @click.stop="clicked">
		<v-list-item-action>
			<v-icon>{{icon}}</v-icon>
		</v-list-item-action>
		<v-list-item-content>
			<v-list-item-title>
				<slot></slot>
			</v-list-item-title>
		</v-list-item-content>
	</v-list-item>
</template>
<script>
export default {
	props: ['icon', 'text', 'route', 'click'],
	data: () => ({}),
	methods: {
		clicked: function() {
			if (typeof this.route == 'string') {
				this.$router.push({ name: this.route }).catch(err => {})
			}
			if (typeof this.click == 'function') {
				this.click();
			}
		}
	},
	watch: {}
}
</script>