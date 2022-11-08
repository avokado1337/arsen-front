<script>

export default {
    data() {
        return {
            registerActive: false,
            emailLogin: "",
            passwordLogin: "",
            emailReg: "",
            passwordReg: "",
            confirmReg: "",
            emptyFields: false
        }
    },
    methods: {
        doLogin() {
            if (this.emailLogin === "" || this.passwordLogin === "") {
                this.emptyFields = true;
            } else {
                alert("You are now logged in");
            }
        },

        doRegister() {
            if (this.emailReg === "" || this.passwordReg === "" || this.confirmReg === "") {
                this.emptyFields = true;
            } else {
                alert("You are now registered");
            }
        }
    }
}
</script>

<template>
    <div class="login-page">
    
        <div class="container">
            <div class="row">
                <div id="card-login-wrapper" class="col-lg-4 col-md-6 col-sm-8 mx-auto">
                    <div v-if="!registerActive" class="card-login" v-bind:class="{ error: emptyFields }">
                        <h1>Sign In</h1>
                        <form class="form-group">
                            <input v-model="emailLogin" type="email" class="form-control" placeholder="Email" required>
                            <input v-model="passwordLogin" type="password" class="form-control" placeholder="Password"
                                required>
                            <input type="submit" class="btn btn-primary" @click="doLogin">
                            <p>Don't have an account? <a href="#"
                                    @click="registerActive = !registerActive, emptyFields = false">Sign up here</a>
                            </p>
                        </form>
                    </div>

                    <div v-else class="card-register" v-bind:class="{ error: emptyFields }">
                        <h1>Sign Up</h1>
                        <form class="form-group">
                            <input v-model="emailReg" type="email" class="form-control" placeholder="Email" required>
                            <input v-model="passwordReg" type="password" class="form-control" placeholder="Password"
                                required>
                            <input v-model="confirmReg" type="password" class="form-control"
                                placeholder="Confirm Password" required>
                            <input type="submit" class="btn btn-primary" @click="doRegister">
                            <p>Already have an account? <a href="#"
                                    @click="registerActive = !registerActive, emptyFields = false">Sign in here</a>
                            </p>
                        </form>
                    </div>
                </div>
            </div>

        </div>
    </div>

</template>

<style scoped lang="less">

.container {
    background-color: white;
    padding: 30px;
    width: 90vh;
    display: flex;
    align-items: center;
}


p {
   line-height: 1rem;
}

.card {
   padding: 20px;
}

.card-login {
    width: 300px;
}

.card-register {
    width: 300px;
}

.form-group {
    display: flex;
    flex-direction: column;
   input {
      margin-bottom: 20px;
   }
}

.login-page {
   align-items: center;
   justify-content: center;
   display: flex;
   
   .fade-enter-active,
   .fade-leave-active {
  transition: opacity .5s;
}
   .fade-enter,
   .fade-leave-to {
      opacity: 0;
   }

   h1 {
      margin-bottom: 1.5rem;
   }
}

.error {
   animation-name: errorShake;
   animation-duration: 0.3s;
}

@keyframes errorShake {
   0% {
      transform: translateX(-25px);
   }
   25% {
      transform: translateX(25px);
   }
   50% {
      transform: translateX(-25px);
   }
   75% {
      transform: translateX(25px);
   }
   100% {
      transform: translateX(0);
   }
}
</style>