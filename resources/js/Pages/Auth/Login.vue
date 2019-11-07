<template>
    <div class="container">
        <div class="row">
            <div class="col-md-8">
                <div class="card">
                    <div class="card-header">
                        <h2>Login</h2>
                    </div>
                    <div class="card-body">
                        <form method="POST" @submit.prevent="login">
                            <div class="form-group">
                                <label for="email">Email</label>
                                <input type="email" name="email" id="email" class="form-control" v-model="form.email">
                            </div>
                            <div class="form-group">
                                <label for="password">Password</label>
                                <input type="password" name="password" id="password" v-model="form.password" class="form-control">
                            </div>
                            <div class="form-group">
                                <button type="submit" class="btn btn-primary">Login</button>
                            </div>
                        </form>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import Layout from "../../Shared/Layout";
export default {
    layout: Layout,
    data() {
        return {
            form: {
                email: "",
                password: ""
            }
        }
    },
    methods: {
        login() {
            this.$inertia.post("/login", this.form)
        }
    }
}
</script>

<style>

</style>
