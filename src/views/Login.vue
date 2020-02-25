<template>
    <div id="login">
        <h1>LOGIN</h1>
        <form class="">
        <div class="form-group">
            <label for="exampleInputEmail1">USERNAME</label>
            <input type="text" class="form-control" name="username" v-model="input.username" placeholder="Username" />
        </div>
        <div class="form-group">
            <label for="exampleInputPassword1">PASSWORD</label>
             <input type="password" class="form-control" name="password" v-model="input.password" placeholder="Password" />
        </div>
        <br>
        <button type="button" class="btn btn-primary" v-on:click="login()">LOGIN</button>
        </form>
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
                        this.$router.replace({ name: "Secure" });
                    } else {
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
        width: 600px;
        background-color: transparent;
        margin: auto;
        margin-top: 200px;
        padding: 50px;
        color: teal;
        font-family: monospace;
        font-size: 30px;
        border-radius: 50px;
        box-shadow: 10px 15px 30px 0 teal;
    }

    .form-group {
        text-align: left;
        color: teal;
        font-family: monospace;
        font-size: 15px;
    }

    .form-control {
        border-radius: 50px;
        padding: 30px;
    }

    .btn-primary {
        width: 200px;
        margin: auto;
        padding: 20px;
        border: 5px double teal;
        border-radius: 50px;
        background-color: deepskyblue;
        color: white;
    }

    .btn-primary:hover {
        border: 5px double teal;
        background-color: transparent;
        color: teal;
    }

</style>