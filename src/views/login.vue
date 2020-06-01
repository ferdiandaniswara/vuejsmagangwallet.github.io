<template>
    <div id="login">
        <div>
        <b-avatar variant="info"></b-avatar><h1>Login</h1>
        <b-form-group id="input-group-2" label="Nama" label-for="input-2">
        <b-form-input
            id="input-2"
            v-model="input.username"
            required
            name="username"
            placeholder="Masukan Nama"
            ></b-form-input>
        </b-form-group>
            <b-form-group id="input-group-3">
                <b-form @submit.stop.prevent>
                <label for="text-password">Password</label>
                <b-input type="password" id="text-password" aria-describedby="password-help-block" v-model="input.password" name="password" placeholder="Masukan Password"></b-input>
            </b-form>
            </b-form-group>
            <b-button variant="info" v-on:click="login()">Login</b-button>
        </div>

    </div>
    
</template>

<script>
    export default {
        name: 'Login',
        data() {
            return {
                input: {
                    username: "",
                    password: ""
                }
            }
        },
        methods: {
            login() {
                if(this.input.username != "" && this.input.password != "") {
                    if(this.input.username == this.$parent.mockAccount.username && this.input.password == this.$parent.mockAccount.password) {
                        this.$emit("authenticated", true);
                        this.$router.replace({ name: "secure" });
                    } else if(this.input.username == this.$parent.mockAccount2.username && this.input.password == this.$parent.mockAccount2.password) {
                        this.$emit("authenticated", true);
                        this.$router.replace({ name: "secure" });
                    }
                        else {
                        console.log("The username and / or password is incorrect");
                    }
                } else {
                    console.log("A username and password must be present");
                }
            }
        }
    }
</script>

<style scoped>
    #login {
        width: 500px;
        border: 25px solid rgb(46, 172, 184);
        background-color: #FFFFFF;
        margin: auto;
        margin-top: 100px;
        border-radius: 30px;
        font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
        padding: 20px;
        box-shadow: 40px 40px 45px rgba(0, 0, 0, 0.3);
        
    }
</style>