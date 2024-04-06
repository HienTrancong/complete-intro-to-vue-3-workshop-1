<script>
import UserCard from './UserCard.vue'
export default {
	components: {
		UserCard
	},
	data: () => ({
		userList: [1, 2, 3]
	}),
	methods: {
		async fetchUserData() {
			this.userList = await fetch('https://jsonplaceholder.typicode.com/users').then(
				response => response.json())
		}
	},
	created() {
		this.fetchUserData()
	}
};
</script>
<template>
	<h1>User</h1>
	<ul>
		<UserCard v-for="user in userList" :user="user" :key="`user-${user.id}`" />
	</ul>

</template>
<style></style>