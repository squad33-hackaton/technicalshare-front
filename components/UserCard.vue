<template>
  <div class="user-card">
		<!-- <img src="" alt="" class="user-card-avatar">  -->
		<font-awesome-icon icon="fa-solid fa-user" style="font-size: 3rem;" />
		<div class="user-card-texts">
			<p><b>{{ username }}</b></p>
			<p>{{ position 	}}</p>
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
.user-card {
  background-color: #dddddd;
  display: flex;
  align-items: center;
  border-radius: 15px;
  gap: 1rem;
  padding: 20px 40px  ;
  max-width: 50%;
	margin: 10px;
}

.user-card-texts p {
  margin: 0;
}
</style>