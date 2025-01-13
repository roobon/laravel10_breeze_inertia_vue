<script setup>
import { Link, usePage, useForm } from "@inertiajs/vue3";

//const {posts}= usePage().props
const form = useForm({});

const deletePost = (id) => {
    //form.delete(route("posts.destroy", { id }));
     form.delete(`posts/${id}`)
};

defineProps({
    posts: {
        type: Array,
        default: () => [],
    },
});
</script>
<template>
    <div class="container">
        <h1 class="display-1">Welcome to Vue with Laravel</h1>
        <table class="table table-bordered">
            <thead>
                <tr>
                <th>ID</th>
                <th>Title</th>
                <th>Details</th>
                <th>Action</th>
            </tr>
            </thead>
            <tbody>
                <tr v-for="x in posts" :key="x.id">
                <td>{{ x.id }}</td>
                <td>{{ x.title }}</td>
                <td>{{ x.body }}</td>
                <td>
                    <Link :href="route('posts.edit', x.id)"
                        ><i class="fa fa-cloud"></i
                    ></Link>
                    &nbsp;
                    <button @click="deletePost(x.id)">
                        <i class="fa fa-trash"></i>
                    </button>
                </td>
            </tr>
            </tbody>
        </table>
        <Link :href="route('posts.create')" class="btn btn-success"
            >New Entry</Link
        >
    </div>
</template>
