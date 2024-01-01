<template>
  <!-- <div class="center">
    <div class="form">
      <div class="fom-element">
        <input :type="type" v-model="userPassword" id="password-field" />
        <div class="toggle-password" @click="changeType()">
          <i
            class="fa fa-eye"
            v-if="type === 'password'"
            aria-hidden="true"
          ></i>
          <i class="fa fa-eye-slash" v-else></i>
        </div>
      </div>
      {{ userPassword }}
       to way binding 
    </div>
  </div>  -->
  <formBuilder key="componentKey" class="form-builder" />
</template>
<script>
import formBuilder from "./components/formBuilder.vue";
export default {
  name: "App",
  components: {
    formBuilder,
  },
  data() {
    return {
      componentKey: 0,
      type: "password",
      userPassword: "",
      formField: {
        userName: "",
        password: "",
        email: "",
        phoneNumber: "",
        genderType: "",
        postalCode: "",
        address: "",
        birthDate: "",
      },
    };
  },
  methods: {
    changeType() {
      console.log("start");
      this.type == "password" ? (this.type = "text") : (this.type = "password");
    },
    forceRerender() {
      this.componentKey += 1;  
    }
  },
};
</script>
<style scoped lang="scss">
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
/* .form {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
.fom-element {
  background-color: rgb(167, 8, 167);
  display: flex;
  align-items: center;
  color: white;
  border-radius: 1rem;
  padding: 1rem;
}
.fom-element input {
  background-color: rgb(167, 8, 167);
  border-radius: 1rem;
  color: white;
  font-size: 1.5rem;
  outline: none;
  border: none;
}
.toggle-password {
  cursor: pointer;
} */
</style>
