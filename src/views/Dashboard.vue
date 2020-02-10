<template>
	<v-container fluid>
		<v-row justify="space-between" align="flex-start">
			<v-col cols="12">
				<h1>Dashboard</h1>
				<p>{{ message }}</p>
			</v-col>
			<v-col cols="12" md="3" sm="6">
				<v-card width="100%">
					<v-card-title primary-title>
						<h3>Interactivity</h3>
					</v-card-title>
					<v-card-text>
						You clicked the button {{ counter }} times.<br>
					</v-card-text>
					<v-card-actions>
						<v-btn color="primary" @click="counter = counter + 1">Add <v-icon>fas fa-plus-circle</v-icon>
						</v-btn>
						<v-btn @click="counter = counter + 10">Add +10</v-btn>
						<v-btn fab small @click="counter = counter - 1">
							<v-icon>fas fa-minus-circle</v-icon>
						</v-btn>
					</v-card-actions>
				</v-card>
			</v-col>
			<v-col cols="12" md="3" sm="6">
				<v-card width="100%">
					<v-card-title primary-title>
						<h3>Test1</h3>
					</v-card-title>
					<v-card-text>
						?
					</v-card-text>
					<v-card-actions>
					</v-card-actions>
				</v-card>
			</v-col>
			<v-col cols="12" md="3" sm="6">
				<v-card width="100%">
					<v-card-title primary-title>
						<h3>Test2</h3>
					</v-card-title>
					<v-card-text>
						??
					</v-card-text>
					<v-card-actions>
					</v-card-actions>
				</v-card>
			</v-col>
		</v-row>
	</v-container>
</template>
<script>
export default {
	name: 'Dashboard',
	props: [],
	data: function() {
		return {
			message: 'You loaded this page on ' + new Date().toLocaleString(),
			counter: 0
		}
	},
	computed: {

	},
	methods: {

	},
	watch: {

	}
}
</script>