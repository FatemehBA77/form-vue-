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
          <button @click="showContenet">Submit</button>
          <button v-if="hasshowresetbtn" @click="resetformefields">
            reset
          </button>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "formBuilder",
  data() {
    return {
      formBuild: {
        id: 0,
        userName: "",
        password: "",
        email: "",
        phoneNumber: "",
        postalCode: "",
        address: "",
        birthDate: "",
      },
      hasshowresetbtn: false,
      numberMax: 100000,
    };
  },
  methods: {
    showContenet() {
      this.hasshowresetbtn = true;
      console.log(this.getAllUsers());
      this.setUserToLocalStorage(this.formBuild);
    },
    resetformefields() {
      this.formBuild = {
        id: Date.now(),
        userName: "",
        password: "",
        email: "",
        phoneNumber: "",
        postalCode: "",
        address: "",
        birthDate: "",
      };
      this.hasshowresetbtn = false;
    },
    getAllUsers() {
      return localStorage.getItem("users") ? localStorage.getItem("users") : [];
    },
    setUserToLocalStorage(user) {
      this.userList.push(user);
      let users = this.getAllUsers();
      localStorage.setItem("users", JSON.stringify(users));
      users.push(user);
      // localStorage.setItem("users", JSON.stringify(user));
      // console.log(localStorage.getItem("users"));
      // console.log(users);
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
