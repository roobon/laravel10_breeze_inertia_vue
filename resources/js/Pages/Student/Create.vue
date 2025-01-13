<script setup>
    import axios from 'axios';

</script>

<script>
   export default{
    data() {
        return {
           name:'',
           dob: '',
           address: '',
           gender: '', 
           district: '',
           languages: []
        }
        
    },
    methods: {
       async submit(){
           await axios.post('http://127.0.0.1:8000/students/store', {
                name:this.name,
                dob:this.dob,
                address:this.address,
                gender:this.gender,
                district:this.district,
                languages:this.languages

            }).then(function (response) {
                console.log(response.msg);
            })
        }
    },
   }


</script>


<template>
    <div>{{ name }}</div>
     <div class="container">
       <br>
  <form @submit.prevent="this.submit" class="form">
                            <div class="mb-4 form-group">
                                <label
                                    
                                    class="block text-gray-700 text-sm font-bold mb-2">
                                    Name:</label>
                                <input
                                    type="text"
                                    class="form-control"
                                    placeholder="Enter Name"
                                    v-model="name"
                                     />

                            </div>

                            <div class="mb-4 form-group">
                                <label
                                    
                                    class="block text-gray-700 text-sm font-bold mb-2">
                                    Address:</label>
                                <textarea
                                    class="form-control" 

                                    placeholder="Enter Address" v-model="address"></textarea>
                            </div>
                            <div class="mb-4 form-group">
                                <label
                                    
                                    class="block text-gray-700 text-sm font-bold mb-2">
                                    Date of Birth:</label>
                                <input
                                    type="date"
                                    class="form-control"
                                    placeholder="Enter Date of Birth"
                                    id="dob" v-model="dob"
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
                                    
                                    value="male" v-model="gender"
                                     />Male &nbsp;
                                     <input
                                    type="radio"
                                    class="form-control"
                                     name="gender"
                                   
                                    value="female" v-model="gender"
                                     />Female
                            </div>
                            <div class="mb-4 form-group">
                                <label
                                    
                                    class="block text-gray-700 text-sm font-bold mb-2">
                                    District:</label>
                                    <select class="form-control" name=""  v-model="district">
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
                                    name="language"
                                    
                                    value="PHP" v-model="language"
                                     /> PHP &nbsp;
                                     <input
                                    type="checkbox"
                                    class="form-control"
                                    name="language"
                                    
                                    value="Javascript" v-model="language"
                                     /> Javascript &nbsp;
                                     <input
                                    type="checkbox"
                                    class="form-control"
                                    name="language"
                                   
                                    value="Laravel" v-model="language"
                                     /> Laravel &nbsp;
                                     <input
                                    type="checkbox"
                                    class="form-control"
                                    name="language"
                                   
                                    value="React" v-model="language"
                                     /> React
                            </div>
                            <div class="mb-4 form-group">
                                <label
                                   
                                    class="block text-gray-700 text-sm font-bold mb-2">
                                    Photo:</label>
                                <input
                                    type="file"
                                    class="form-control"
                                    name="photo"
                                     
                                     />
                            </div>
                            <button type="submit" class="btn btn-success">
                                Submit
                            </button>

                        </form>
                    </div>


</template>