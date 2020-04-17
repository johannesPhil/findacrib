<template>
  <b-container fluid>
    <b-row class="text-center" id="register-hero">
      <Navigation />
      <b-row id="register-hero-content">
        <b-col sm="6" align-self="center">
            <b-row class="text-container">
              <h2 class="text">Rent Out Your Free Apartment</h2>
            </b-row>
            <b-row class="text-container">
              <h2 class="text">Cash Out</h2>
            </b-row>
        </b-col>
        <b-col sm="6">
          <b-row>
            <b-form ref="registerForm" @submit.prevent="registerUser" class="text-left" id="frost-form" novalidate="true">
              <b-col sm>
                <b-col class="form-control-container">
                  <label for="name">Your Name<small>(Required)</small></label>
                  <b-form-input type="text" id="name" v-model="name" ref="name" placeholder="Your personal/agency name" required></b-form-input>
                </b-col>
                <b-col class="form-control-container">
                  <label for="phone">Phone Number<small>(Required)</small></label>
                  <b-form-input type="tel" id="phone" v-model="phone" ref="phone" placeholder="Phone Number" required></b-form-input>
                </b-col>
                <b-col class="form-control-container">
                  <label for="mail">Email Address<small>(Required)</small></label>
                  <b-form-input type="email" id="mail" v-model="mail" ref="mail" placeholder="Email Address" required></b-form-input>
                </b-col>
                <b-col class="form-control-container">
                  <label for="password">Password<small>(Required)</small></label>
                  <b-form-input type="password" id="password" v-model="password" ref="pass1" placeholder="Password" required></b-form-input>
                </b-col>
                <b-col class="form-control-container">
                  <label for="confirm_pass">Confirm Password<small>(Required)</small></label>
                  <b-form-input type="password" id="confim_pass" v-model="confirmPass" ref="pass2" placeholder="Confirm Password" required></b-form-input>
                </b-col>
                <p v-if="errors.length">
                  <b>Please address the following issues:</b>
                  <ul>
                    <li v-for="error in errors" :key="error">{{ error }}</li>
                  </ul>
                </p>
                <b-col class="form-control-container">
                  <b-button type="submit" variant="info">Become a Lister!</b-button>
                </b-col>
              </b-col>
            </b-form>
          </b-row>
        </b-col>
        
      </b-row>
    </b-row>
    <b-row class="section">
      <b-col cols="10" offset="1">
        <h2 class="section-header">Why List Your Apartment Here?</h2>
        <p class="section-par">
          Lorem, ipsum dolor sit amet consectetur adipisicing elit. Nulla, ratione voluptas temporibus voluptatum cupiditate 
          rem maxime velit inventore. Id commodi consectetur quae reiciendis at accusantium magni incidunt veniam. Suscipit, 
          perferendis.
        </p>
        <p class="section-par">
          Lorem, ipsum dolor sit amet consectetur adipisicing elit. Nulla, ratione voluptas temporibus voluptatum cupiditate 
          rem maxime velit inventore. Id commodi consectetur quae reiciendis at accusantium magni incidunt veniam. Suscipit, 
          perferendis.
        </p>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import Navigation from '../components/Navigation'
export default {
  components: {
    Navigation
  },
  data () {
    return {
      errors: '',
      name: '',
      phone: '',
      mail: '',
      password: '',
      confirmPass: '',
    }
  },
  methods: {
    registerUser () {
      this.errors = []
      if(!this.name){
        this.errors.push('Name is empty, fill it up')
        this.$refs.name.focus()
        return false
      }
      else if(!this.validName(this.name)){
        this.errors.push('The name you used is invalid, please check')
        this.$refs.name.focus()
        return false
      }

      if(!this.phone) {
        this.errors.push('Phone number is empty, fill it up')
        this.$refs.phone.focus()
        return false
      }
      else if(!this.validPhone(this.phone)) {
        this.errors.push('Phone number is neither a Nigerian landline or mobile number, fix it')
        this.$refs.phone.focus()
        return false
      }

      if(!this.mail) {
        this.errors.push('Email address field is empty, fill it up')
        this.$refs.mail.focus()
        return false
      }
      else if(!this.validMail(this.mail)) {
        this.errors.push('Invalid email address')
        this.$refs.mail.focus()
        return false
      }

      if(!this.password) {
        this.errors.push('Password field is empty, fill it up')
        this.$refs.pass1.focus()
        return false
      }
      else if(!this.validPassword(this.password)) {
        this.errors.push('Password should contain at least six(6) characters')
        this.$refs.pass1.focus()
        return false
      }

      if(!this.confirmPass) {
        this.errors.push(`The 'Confirm Password' field is empty, fill it up`)
        this.$refs.pass2.focus()
        return false
      }
      else if(this.confirmPass !== this.password) {
        this.errors.push('Passwords do not match, make sure they do')
        this.$refs.pass2.focus()
        return false
      }

      var axiosOpt = {
            headers: {
                'Content-Type': 'application/x-www-form-urlencoded'
            }
        }

      this.$axios.post('https://findheim.000webhostapp.com/add_agent.php',{

        name: this.name,
        phone: this.phone,
        mail: this.mail,
        password: this.password
        
      }, axiosOpt)
      .then(response =>{
        console.log(response.statusText)
      })
      .catch(error => {
        console.log(error)
      })
    },

    // Name validation
    validName (name) {
      let nameRegEx = /^([a-zA-Z0-9]+|[a-zA-Z0-9]+\s{1}[a-zA-Z0-9]{1,}|[a-zA-Z0-9]+\s{1}[a-zA-Z0-9]{3,}\s{1}[a-zA-Z0-9]{1,})$/
      return nameRegEx.test(name)
    },

    //Phone number validation
    validPhone (phoneNumber) {
      let phoneRegEx = /^[0-9]{6,}$/
      return phoneRegEx.test(phoneNumber)
    },

    // Email validation
    validMail (mail) {
      let mailRegEx = /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/
      return mailRegEx.test(mail)
    },
    validPassword (password) {
      let passRegEx = /(?=.*[A-Za-z0-9]).{6,}$/
      return passRegEx.test(password)
    }
  }
}
</script>

<style>
body{
  width: 100%;
  height: auto;
  overflow: auto;
  font-family: "Fira Sans", sans-serif;
  background-color: #f5f9fc;
}
#register-hero {
  position: relative;
  min-height: 600px;
  background-image: url("../static/key.jpg");
  background-position: center;
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-size: cover;
  color: #ffffff;
}
#register-hero-content{
  width: 100%;
  margin: 0;
  padding: 15px;
}
.text-container{
  text-align: left;
}
.text{
  font-size: 2.5rem;
  font-weight: bolder;
  margin: 2rem 0;
  text-shadow: 0px 1px 1px black;
}
#frost-form{
  position: relative;
  width: 90%;
  margin: auto;
  height: fit-content;
  background: inherit;
  overflow: hidden;
}
#frost-form::before{
  content: '';
  position: absolute;
  background: inherit;
  left: 0;
  right: 0;
  top: 0;
  bottom: 0;
  box-shadow: inset 0 0 0 3000px rgba(90, 87, 87, 0.795);
  filter: blur(200px);
}
.form-control-container{
  margin: 1rem 0;
}
.form-control{
  height: 3rem;
}
.section{
  width: 90%;
  margin: 3em auto;
  padding:3em 0;
  display: block;
  background-color: #ffffff;
  line-height: 2em;
  border-radius: 10px;
  box-shadow: 0 0px 8px 0 rgba(41, 41, 41, 0.178);
}
.section-header::after{
  display: block;
  content: '';
  position: absolute;
  width: 100%;
  border-bottom: solid .05rem teal;
}
.section-par{
  display: block;
}
</style>
