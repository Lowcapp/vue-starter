<template>
  <div>
	<h1>Witaj w systemie do zapisów na zajęcia</h1>
    <div v-if="authenticatedEmail != ''">
	ZALOGOWANY
	<H4>Jeseś zalogowany jako {{ authenticatedEmail }}</H4>
	<a @click="logMeOut()">Wyloguj</a>
    </div>
    <div v-else>
	<login-form @login="logMeIn($event)"></login-form>
    </div>
  </div>
</template>

<script>
import LoginForm from "./LoginForm";
import "milligram";
export default {
	data() {
	  return {
		authenticatedEmail: '',
      };
	},
	methods: {
      logMeIn(username) {
        this.authenticatedEmail = username;
      },
	   logMeOut() {
        this.authenticatedEmail = '';
		this.email = '';
      }
    },
	components: {LoginForm},
};
</script>

<style>

</style>
