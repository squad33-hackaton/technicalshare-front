<template>
  <div class="user-card" @click="$emit('click')">
		<!-- <img src="" alt="" class="user-card-avatar">  -->
		<font-awesome-icon icon="fa-solid fa-user" style="font-size: 3rem;" />
		<div class="user-card-texts">
			<p><b>{{ username }}</b></p>
			<p>{{ position }}</p>
		</div>
	</div>
</template>

<script>
export default {
	name: "UserCard",
	props: {
		username:	{
			type: String,
			required: true
		},
		position: {
			type: String,
			required: true
		}
	}
}
</script>

<style scoped>
p {
  font-family: 'Manrope'
}

.user-card {
  background-color: #ffffff;
  display: flex;
  align-items: center;
  border-radius: 15px;
  gap: 1rem;
  padding: 40px 60px;
  max-width: 50%;
  margin: 10px;
  cursor: pointer;
	box-shadow: rgba(99, 99, 99, 0.2) 0px 2px 8px 0px;
}

.user-card:hover {
	background-color: #A6A3A3;
}

.user-card-texts p {
  margin: 0;
}
</style>