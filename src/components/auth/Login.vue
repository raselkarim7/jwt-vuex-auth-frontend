<template>
    <div class="flex-row align-items-center">
        <div class="container">
            <div class="col-md-6 col-sm-8">
                <div class="mx-4">
                    <div class="p-4 card bg-warning">
                        <h1>Login Formsss</h1>

        <form class="login" @submit.prevent="login">
            <h1>Sign in</h1>
            
            <label>Email</label>
            <input v-model="email" type="text" placeholder="Name"/>

            <label>Password</label>
            <input v-model="password" type="password" placeholder="Password"/>
            <hr/>
            <button type="submit">Login</button>
        </form>

                    </div>

                </div>

            </div>

        </div>

    </div>
</template>

 <script>
      export default {
        data() {
          return {
            email: "",
            password: ""
          };
        },
        methods: {
          login: function() {
            console.log('1. Login method called.');
            let email = this.email;
            let password = this.password;
            this.$store
              .dispatch("login", { email, password })
              .then((response) => {
                //console.log('Login Success ===== ', response)
                this.$router.push({path: '/' })
                })
              .catch(err => console.log('Login :: Failed --->', err, err.response));
          }
        }
      };
      </script>

<style>

</style>
