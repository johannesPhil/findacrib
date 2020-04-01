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
            <b-form @submit.prevent="registerUser" class="text-left" id="frost-form">
              <b-col sm>
                <b-col class="form-control-container">
                  <label for="name">Your Name<small>(Required)</small></label>
                  <b-form-input type="text" id="name" v-model="reg.name" description="Your personal/agency name"></b-form-input>
                </b-col>
                <b-col class="form-control-container">
                  <label for="phone">Phone Number<small>(Required)</small></label>
                  <b-form-input type="tel" id="phone" v-model="reg.phone"></b-form-input>
                </b-col>
                <b-col class="form-control-container">
                  <label for="mail">Email Address<small>(Required)</small></label>
                  <b-form-input type="email" id="mail" v-model="reg.mail"></b-form-input>
                </b-col>
                <b-col class="form-control-container">
                  <label for="password">Password<small>(Required)</small></label>
                  <b-form-input type="password" id="password" v-model="reg.password"></b-form-input>
                </b-col>
                <b-col class="form-control-container">
                  <label for="confirm_pass">Confirm Password<small>(Required)</small></label>
                  <b-form-input type="password" id="confim_pass" v-model="reg.confirmPass"></b-form-input>
                </b-col>
                <b-col class="form-control-container">
                  <b-button type="submit" variant="info">Find</b-button>
                </b-col>
              </b-col>
            </b-form>
          </b-row>
        </b-col>
      </b-row>
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
      reg: {
        name: '',
        phone: '',
        mail: '',
        password: '',
        confirmPass: ''
      }
    }
  },
  methods: {
    registerUser () {
      console.log(this.name)
    }
  }
}
</script>

<style scoped>
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
  background: inherit;
  position: absolute;
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
</style>
