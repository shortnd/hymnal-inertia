<template>
    <div>
        <header>
            <nav class="navbar navbar-expand-md navbar-light bg-white shadow-sm">
                <inertia-link class="navbar-brand" href="/">Home</inertia-link>
                <ul class="mr-auto navbar-nav">
                    <li class="nav-item" v-if="$page.user && $page.user.playersAllowed">
                        <inertia-link class="nav-link" href="">Players</inertia-link>
                    </li>
                </ul>
                <ul class="ml-auto navbar-nav">
                    <template v-if="!$page.user">
                        <li class="nav-item">
                            <inertia-link class="nav-link" href="/login">Login</inertia-link>
                        </li>
                        <li class="nav-item">
                            <inertia-link class="nav-link" href="/register">Register</inertia-link>
                        </li>
                    </template>
                    <template v-else>
                        <li>
                            <form method="POST" @submit.prevent="logout">
                                <button type="submit">Logout</button>
                            </form>
                        </li>
                    </template>
                </ul>
            </nav>
        </header>
        <main class="py-4">
            <slot />
        </main>
    </div>
</template>

<script>
import moment from "moment";
export default {
    props: {
        title: String,
    },
    watch: {
        title: {
            immediate: true,
            handler(title) {
                document.title = title || "Laravel"
            }
        },
    },
    computed: {
        date() {
            return moment(this.$page.user.last_login_at).format("MMMM Do YYYY, h:mm:ss a");
        }
    },
    methods: {
        logout() {
            this.$inertia.post('/logout')
        }
    }
}
</script>

<style>

</style>
