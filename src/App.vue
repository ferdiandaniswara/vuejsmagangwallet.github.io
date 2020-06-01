<template>
    <div id="app">
        <div id="nav">
            <router-link v-if="authenticated" to="/login" v-on:click.native="logout()" replace>
            <div>
             <b-navbar toggleable="lg" type="dark" variant="info">
             <b-navbar-brand > <img src="https://i.ibb.co/mXq2C8W/3143358.png" alt="3143358" border="0"></b-navbar-brand>
             <b-collapse id="nav-collapse" is-nav>
                <b-navbar-nav class="ml-auto">
                    <b-navbar-nav>
                    <b-button variant="info">Log Out</b-button>
                </b-navbar-nav>
                </b-navbar-nav>
                </b-collapse>
            </b-navbar>
</div></router-link>
        </div>

        <router-view @authenticated="setAuthenticated" />
          
    </div>
    
</template>
   

              


        


<script>
    export default {
        name: 'App',
        data() {
            return {
                authenticated: false,
                mockAccount:{
                    username: "exy",
                    password: "asdf1234",
                    nama: "Exy",
                },
                mockAccount2: {
                    username: "wartono",
                    password: "asdf1234",
                    nama: "Wartono",

                }
                
            }
                
        },
        mounted() {
            if(!this.authenticated) {
                this.$router.replace({ name: "login" });
            }
        },
        methods: {
            setAuthenticated(status) {
                this.authenticated = status;
            },
            logout() {
                this.authenticated = false;
            }
        }
    }

    
    
</script>

<style>
    body {
        background-color: rgb(253, 253, 253);
    }
    h1 {
        padding: 0;
        margin-top: 0;
    }
</style>