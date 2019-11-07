<template>
    <div class="container">
        <div class="row">
            <div class="col-md-8">
                <div class="card">
                    <div class="card-header">
                        Register
                    </div>
                    <div class="card-body">
                        <form @submit.prevent="register" method="POST">
                            <div class="form-group">
                                <label for="first_name">First Name</label>
                                <input type="text" name="first_name" id="first_name" class="form-control" v-model="form.first_name">
                            </div>
                            <div class="form-group">
                                <label for="last_name">Last Name</label>
                                <input type="text" name="last_name" id="last_name" class="form-control" v-model="form.last_name">
                            </div>

                            <div class="form-group">
                                <label for="email">Email</label>
                                <input type="email" name="email" id="email" class="form-control" v-model="form.email">
                            </div>
                            <div class="form-group">
                                <label for="display_name">Display Name</label>
                                <input type="text" name="display_name" id="display_name" class="form-control" v-model="form.display_name">
                            </div>
                            <div class="form-group row">
                                <label for="password" class="col-md-4 col-form-label text-md-right">Password</label>

                                <div class="col-md-6">
                                        <input id="password" type="password" class="form-control" name="password" required autocomplete="new-password" v-model="form.password">
                                </div>
                            </div>

                            <div class="form-group row">
                                <label for="password-confirm" class="col-md-4 col-form-label text-md-right">Confirm Password</label>

                                <div class="col-md-6">
                                    <input id="password-confirm" type="password" class="form-control" name="password_confirmation" required autocomplete="new-password" v-model="form.password_confirmation">
                                </div>
                            </div>
                            <div class="form-group">
                                <button type="submit" class="btn btn-primary">Register</button>
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
                first_name: "",
                last_name: "",
                email: "",
                display_name: "",
                password: "",
                password_confirmation: ""
            },
        }
    },
    methods: {
        register() {
            this.$inertia.post("/register", this.form)
        }
    }
}
</script>

<style>

</style>
