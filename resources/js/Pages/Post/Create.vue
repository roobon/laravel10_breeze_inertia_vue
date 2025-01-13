<script setup>
import { useForm, Link } from "@inertiajs/vue3";
const form = useForm({
    title: '',
    body: ''
});
const submit = () => {
  form.post("/posts");
};
</script>

<template>
     <div class="container">
       <Link class="btn btn-success"
        :href="route('posts.index')">Post List</Link>
        <form @submit.prevent="submit" class="form">
                            <div class="mb-4 form-group">
                                <label 
                                    for="title" 
                                    class="block text-gray-700 text-sm font-bold mb-2">
                                    Title:</label>
                                <input 
                                    type="text" 
                                    class="form-control" 
                                    placeholder="Enter Title" 
                                    id="title"
                                    v-model="form.title" />

                            </div>

                            <div class="mb-4 form-group">
                                <label 
                                    for="body" 
                                    class="block text-gray-700 text-sm font-bold mb-2">
                                    Body:</label>
                                <textarea 
                                    class="form-control" id="body" 
                                    v-model="form.body" 
                                    placeholder="Enter Body"></textarea>
                            </div>

                            <button type="submit" class="btn btn-info">
                                Submit
                            </button>
                        </form>
     </div>
</template>

