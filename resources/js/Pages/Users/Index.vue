<template>
    <div class="container">
        <ul v-if="users">
            <li v-for="(user, index) in users" :key="index">
                {{ user.first_name }}
            </li>
        </ul>
    </div>
</template>

<script>
import Layout from "../../Shared/Layout";
export default {
    props: ["users"],
    layout: Layout
}
</script>

<style>

</style>
