<template>
		<the-header></the-header>
		<!-- <TheHeader /> -->
		<button @click="setSelectedComponent('active-goals')">Active Goals</button>
		<button @click="setSelectedComponent('manage-goals')">Manage Goals</button>
		<!-- <active-goals v-if="selectedComponent === 'active-goals'"></active-goals>
		<manage-goals v-if="selectedComponent === 'manage-goals'"></manage-goals> -->
		<keep-alive>
			<component :is="selectedComponent"></component>
		</keep-alive>
</template>

<script>
import TheHeader from "./components/layout/TheHeader.vue";
import ManageGoals from "./components/ManageGoals.vue";
import ActiveGoals from "./components/ActiveGoals.vue";

export default {
	components: {
		// 'the-header': TheHeader, =====>
		// TheHeader: TheHeader, ====>
		TheHeader,
		ManageGoals,
		ActiveGoals,
	},
	data() {
		return {
			selectedComponent: "active-goals",
			activeUser: {
				name: "Nikola Bogicevic",
				description: "Site owner and admin",
				role: "admin",
			},
		};
	},
	methods: {
		setSelectedComponent(component) {
			this.selectedComponent = component;
		},
	},
};
</script>

<style>
html {
	font-family: sans-serif;
}

body {
	margin: 0;
}
</style>