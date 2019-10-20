<template>
    <div class="">
        <form>
            <div class="input-wrapper">
                <input type="text" placeholder="Username" name="username" id="username" v-model="username">
            </div>
            <div class="input-wrapper">
                <input type="password" placeholder="Password" name="password" id="password" v-model="password">
            </div>
            <div class="input-wrapper">
                <a @click="login" href="javascript:void(0);">Sign In</a>
            </div>

            <a href="javascript:void(0);" @click="getUsers">biubiu</a>
        </form>
    </div>
</template>

<script>
    import axios from 'axios'
    export default {
        name: "Login",
        data() {
            return {
                username: null,
                password: null
            }
        },
        methods: {
            login() {
                const formData = new FormData();
                formData.append('username', this.username);
                formData.append('password', this.password);
                this.$http.post('http://127.0.0.1:8888/login', formData,{
                    headers: {
                        'Content-Type': 'application/x-www-form-urlencoded'
                    }
                }).then(function (response) {
                    window.console.log(response)
                })
            },
            getUsers() {
                this.$http.get('http://127.0.0.1:8888/users', {
                    headers: {
                        'Authorization':'2223dcde-1c8f-477c-9e9d-8224e78457d2'
                    },
                }).then(function (response) {
                    window.console.log(response);
                })
            }
        },
        watch: {
            username: function (newValue, oldValue) {
                this.username = newValue;
            },
            password: function (newValue, oldValue) {
                this.password = newValue;
            }
        }
    }
</script>

<style scoped>
    .input-wrapper {
        margin: 1rem;
    }

    .input-wrapper input[type=password],input[type=text]  {
        height: 2.4rem;
        width: 18rem;
        border: none;
        border-radius: .2rem;
        line-height: 2.4rem;
        font-size: 1.2rem;
        padding: 0 .5rem;
        box-sizing: border-box;
    }
</style>