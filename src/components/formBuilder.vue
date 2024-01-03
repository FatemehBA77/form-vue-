<template>
  <div class="content">
    <div class="form">
      <div class="form-container">
        <section class="elements">
          <div class="lable__form">
            <div class="lables">
              <label for="username">username:</label>
              <input v-model="formBuild.userName" type="text" id="username" />
            </div>
            <div class="lables">
              <label for="password">Password:</label>
              <input
                v-model="formBuild.password"
                type="password"
                id="password"
              />
            </div>
            <div class="lables">
              <label for="email">Email:</label>
              <input v-model="formBuild.email" type="text" id="email" />
            </div>
            <div class="lables">
              <label for="phone_number">PhoneNumber:</label>
              <input
                v-model="formBuild.phoneNumber"
                type="text"
                id="phone_number"
              />
            </div>
            <div class="lables">
              <label for="postal-code">PostalCode:</label>
              <input
                v-model="formBuild.postalCode"
                type="text"
                id="post-code"
              />
            </div>
            <div class="lables">
              <label for="address">Address:</label>
              <input v-model="formBuild.address" type="text" id="address" />
            </div>
            <div class="lables">
              <label for="birth-date">BirthDate:</label>
              <input v-model="formBuild.birthDate" type="date" name="" id="" />
            </div>
          </div>
          <div class="img_form">
            <img src="../assets/images/1.png" alt="" />
          </div>
        </section>
        <div class="btn btn__primary">
          <button @click="showContenet($event)">Submit</button>
          <button v-if="hasshowresetbtn" @click="resetformefields()">
            reset
          </button>
          <button><router-link to="/foo">show table</router-link></button>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import { v4 as uuidv4 } from "uuid";
export default {
  name: "formBuilder",
  data() {
    return {
      formBuild: {
        id: uuidv4(),
        userName: "",
        password: "",
        email: "",
        phoneNumber: "",
        postalCode: "",
        address: "",
        birthDate: "",
      },
      hasshowresetbtn: false,
    };
  },
  watch: {
    userName(val) {
      if (val) {
        console.log(val);
      }
    },
  },
  methods: {
    showContenet(e) {
      e.preventDefault();
      this.hasshowresetbtn = true;
      const users = this.getAllUsers();
      this.setUserToLocalStorage(this.formBuild);
      console.log(users);
      this.resetformefields();
    },
    resetformefields() {
      this.formBuild = {
        id: uuidv4(),
        userName: "",
        password: "",
        email: "",
        phoneNumber: "",
        postalCode: "",
        address: "",
        birthDate: "",
      };
      console.log("object :>> ", this.formBuild);
      this.hasshowresetbtn = false;
    },
    getAllUsers() {
      return JSON.parse(localStorage.getItem("users")) || [];
    },
    setUserToLocalStorage(user) {
      let userAll = this.getAllUsers();
      userAll.push(user);
      localStorage.setItem("users", JSON.stringify(userAll));
    },
    uniqeNumber() {
      return Math.floor(Math.random() * 100);
    },
  },
};
</script>
<style scoped lang="scss">
@import url(../assets/css/font.css);
*,
body {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: Poppins;
}
.content {
  width: 100%;
  height: 97vh;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}
.form {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
}
.form-container {
  width: 50%;
  background-color: rgb(214, 213, 213);
  border-radius: 7px;
}
.elements {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.lable__form {
  // background-color: brown;
  width: 100%;
}
.lables {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem;
  input {
    outline: none;
    border: none;
    padding: 12px 13px;
    border-radius: 8px;
  }
}
.btn {
  padding: 1rem;
  display: flex;
  justify-items: center;
  justify-content: flex-end;
  button {
    border: none;
    outline: none;
    padding: 12px;
    color: white;
    background-color: rgba(57, 5, 100, 0.822);
    border-radius: 8px;
    cursor: pointer;
  }
}
</style>
