<script setup>
import { useForm } from '@inertiajs/vue3';

    const form = useForm(
        {
           name:'',
           dob: '',
           address: '',
           gender: '', 
           district: '',
           langs: [],
           photo:null
        }
    );

    const submit = ()=>{
        form.post("/students")
    }

</script>




<template>
    <div>{{ name }}</div>
     <div class="container">
       <br>
  <form @submit.prevent="submit" class="form" enctype="multipart/form-data">
                            <div class="mb-4 form-group">
                                <label
                                    
                                    class="block text-gray-700 text-sm font-bold mb-2">
                                    Name:</label>
                                <input
                                    type="text"
                                    class="form-control"
                                    placeholder="Enter Name"
                                    v-model="form.name"
                                     />

                            </div>

                            <div class="mb-4 form-group">
                                <label
                                    
                                    class="block text-gray-700 text-sm font-bold mb-2">
                                    Address:</label>
                                <textarea
                                    class="form-control" 

                                    placeholder="Enter Address" v-model="form.address"></textarea>
                            </div>
                            <div class="mb-4 form-group">
                                <label
                                    
                                    class="block text-gray-700 text-sm font-bold mb-2">
                                    Date of Birth:</label>
                                <input
                                    type="date"
                                    class="form-control"
                                    placeholder="Enter Date of Birth"
                                    id="dob" v-model="form.dob"
                                     />
                            </div>
                            <div class="mb-4 form-group">
                                <label
                                    
                                    class="block text-gray-700 text-sm font-bold mb-2">
                                    Gender:</label>
                                <input
                                    type="radio"
                                    class="form-control"
                                     name="gender"
                                    
                                    value="male" v-model="form.gender"
                                     />Male &nbsp;
                                     <input
                                    type="radio"
                                    class="form-control"
                                     name="gender"
                                   
                                    value="female" v-model="form.gender"
                                     />Female
                            </div>
                            <div class="mb-4 form-group">
                                <label
                                    
                                    class="block text-gray-700 text-sm font-bold mb-2">
                                    District:</label>
                                    <select class="form-control" name=""  v-model="form.district">
                                      <option disabled value="">Select one</option>
                                      <option>Dhaka</option>
                                      <option>Narayanganj</option>
                                      <option>Cumilla</option>
                                      <option>Chittagong</option>
                                    </select>
                            </div>
                            <div class="mb-4 form-group">
                                <label
                                    
                                    class="block text-gray-700 text-sm font-bold mb-2">
                                    Language:</label>
                                <input
                                    type="checkbox"
                                    class="form-control"
                                   
                                    
                                    value="PHP" v-model="form.langs"
                                     /> PHP &nbsp;
                                     <input
                                    type="checkbox"
                                    class="form-control"
                                    
                                    
                                    value="Javascript" v-model="form.langs"
                                     /> Javascript &nbsp;
                                     <input
                                    type="checkbox"
                                    class="form-control"
                                    
                                   
                                    value="Laravel" v-model="form.langs"
                                     /> Laravel &nbsp;
                                     <input
                                    type="checkbox"
                                    class="form-control"
                                    
                                   
                                    value="React" v-model="form.langs"
                                     /> React
                            </div>
                            <div class="mb-4 form-group">
                                <label
                                   
                                    class="block text-gray-700 text-sm font-bold mb-2">
                                    Photo:</label>
                                <input
                                    type="file"
                                    class="form-control" @input="form.photo = $event.target.files[0]"
                                     />
                            </div>
                            <button type="submit" class="btn btn-success">
                                Submit
                            </button>

                        </form>
                    </div>


</template>