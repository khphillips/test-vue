<template>
	<div class="home">
		<v-container class="fill-height" fluid>
			<v-row justify="space-between" align="start">
				<v-col cols="6">
					<v-card width="100%">
						Test
					</v-card>
				</v-col>
				<v-col cols="3">
					<v-card width="100%">
						Test
					</v-card>
				</v-col>
				<v-col cols="3">
					<v-card width="100%">
						Test
					</v-card>
				</v-col>
			</v-row>
		</v-container>
	</div>
</template>
<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
	name: 'Home',
	components: {
		HelloWorld
	}
}
</script>