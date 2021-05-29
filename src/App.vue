<template>
  <div>
	<h1>Witaj w systemie do zapisów na zajęcia</h1>
  <div v-if="authenticatedEmail != ''">
	ZALOGOWANY
	<H4>Jeseś zalogowany jako {{ authenticatedEmail }}</H4>
	<a @click="logMeOut()">Wyloguj</a>
  </div>
  <div v-else>
	Wpisz login:
	<input type="text" v-model="email"> <button @click="logMeIn()">Wchodzę</button>
  </div>
  </div>
</template>

<script>
export default {
	data() {
	  return {
	    email: 'ppietraszek@student.agh.edu.pl',
		authenticatedEmail: '',
	    password: ''
      };
	},
	methods: {
      logMeIn() {
        this.authenticatedEmail = this.email;
      },
	   logMeOut() {
        this.authenticatedEmail = '';
		this.email = '';
      }
    }
	
};
</script>

<style>

</style>
