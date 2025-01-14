<template>
    <div class="container">
        <Link class="btn btn-success" :href="route('students.create')" >New Student</Link>
        <table class="table table-bordered">
            <thead>
                <tr>
                    <th></th>
                    <th></th>
                    <th></th>
                    <th></th>
                    <th></th>
                    <th></th>
                    <th></th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="x in students" :key="x.id">
                    <td>{{x.id  }}</td>
                    <td>{{x.name  }}</td>
                    <td>{{x.dob  }}</td>
                    <td>{{x.address  }}</td>
                    <td>{{x.gender  }}</td>
                    <td>{{x.district  }}</td>
                    <td>
                       {{ LangConvert(x.languages) }}

                    </td>
                    <td><img :src="x.photo" alt="" width="150"></td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script setup>
import { Link } from '@inertiajs/vue3';

    defineProps({
       students:{
        type:Array,
        default:()=>[]
       }, 
       languages:{
        type:Array,
        default:()=>[]
       }, 
    })

    const LangConvert = (lang)=>{
        return JSON.parse(lang).join(', ');
    }
</script>

<style scoped>

</style>