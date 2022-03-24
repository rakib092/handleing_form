<template>
    <div>
        <form>
           <div class="row">
             <div class="col-md-6">
              <div class="card">
                  <div class="card-header">
                    Form Handle
                  </div>
                  <div class="card-body">
                    <div class="mb-3">
                      <label for="email" class="form-label">Email address</label>
                      <input type="email" class="form-control" id="email" v-model="formData.email">
                    </div>
                    <div class="mb-3">
                      <label for="password" class="form-label">Password</label>
                      <input type="password" class="form-control" id="password" v-model.lazy="formData.password">
                    </div>
                    <div class="mb-3">
                      <label for="age" class="form-label">Age</label>
                      <input type="number" class="form-control" id="age" v-model="formData.age">
                    </div>

                    <div class="mb-3">
                      <label for="message" class="form-label">Message</label>
                      <textarea class="form-control" id="message" rows="3" v-model="formData.message"></textarea>
                    </div>

                    <div class="mb-3">
                        <input type="checkbox" id="SendMail" value="SendMail" v-model="formData.sendMail">
                        <label for="SendMail">SendMail</label>

                        <input type="checkbox" id="SendInformation" value="SendInformation" v-model="formData.sendMail">
                        <label for="SendInformation">SendInformation</label> 
                    </div>

                   <div class="mb-3">
                      <input type="radio" id="Male" value="Male" v-model="formData.gender" />
                      <label for="Male">Male</label>

                      <input type="radio" id="Female" value="Female" v-model="formData.gender" />
                      <label for="two">Female</label>   
                    </div>

                  <div class="mb-3">
                       <select v-model="formData.selected" class="form-control">
                          <option disabled value="">Blood</option>
                          <option v-for="b in formData.blood" :key="b">{{ b }}</option>
                        </select> 
                    </div>

                    <div class="mb-3">
                       <button type="submit" class="btn btn-primary" @click.prevent="submitted">Submit</button>
                    </div>
                  </div>
                </div>
             </div>
           </div> 
        </form>
        <hr>
        <div class="row" v-if="isSubmitted">
            <div class="col-md-6">
              <div class="card">
                <div class="card-header">
                  Show Data
                </div>
                <div class="card-body">
                    <p>Email : {{ formData.email }}</p>
                    <p>Password : {{ formData.password }}</p>
                    <p>Age : {{ formData.age }}</p>
                    <p style="white-space: pre-line;">Message : {{ formData.message }}</p>
                    <p>Send Mail : {{formData.sendMail}}</p>
                    <p>Gender : {{formData.gender}}</p>
                    <p>Blood : {{formData.selected}}</p>
                </div>
              </div>
            </div>
        </div>
    </div>
    

</template>

<script>

export default {
   data() {
     return {
         formData:{
            email:'',
            password:'',
            age:0,
            message:'',
            sendMail:[],
            gender:'Male',
            selected:'A+',
            blood:['A+','B+','O+','AB+']
         },
          isSubmitted:false
     }
   },

   methods:{
       submitted(){
         this.isSubmitted=true;
       } 
   },

}
</script>