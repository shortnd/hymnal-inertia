<template>
    <div class="container">
        <div class="card">
            <div class="card-header">
                <h2>Create User</h2>
            </div>
            <div class="card-body">
                <form @submit.prevent="" method="post">
                    <div class="form-group">
                        <label for="first_name">First Name</label>
                        <input type="text" name="first_name" id="first_name" class="form-control" required>
                    </div>
                </form>
            </div>
        </div>
    </div>
</template>

<script>
import Layout from "../../Shared/Layout"
export default {
    layout: Layout
}
</script>

<style>

</style>
