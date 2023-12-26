<template>
  <div class="content">
    <div class="form">
      <div class="form-container">
        <section class="elements">
          <div class="lable__form">
            <label for="username">username:</label>
            <label for="password">Password:</label>
            <label for="email">Email:</label>
            <label for="phone_number">PhoneNumber:</label>
            <label for="postal-code">PostalCode:</label>
            <label for="address">Address:</label>
            <label for="birth-date">BirthDate:</label>
          </div>
          <div class="input__form">
            <input type="text" id="username" />
            <input type="password" id="password" />
            <input type="text" id="email" />
            <input type="text" id="phone_number" />
            <input type="text" id="post-code" />
            <input type="text" id="address" />
            <date-picker />
          </div>
          <div class="img_form">
            <img src="../assets/images/1.png" alt="" />
          </div>
        </section>
        <div class="btn__primary">
          <button>Submit</button>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import VuePersianDatetimePicker from "vue-persian-datetime-picker";
export default {
  name: "formBuilder",
  data() {
    return {
      formBuild: {
        userName: "",
        password: "",
        email: "",
        phoneNumber: "",
        postalCode: "",
        address: "",
        birthDate: "",
      },
    };
  },
  components: {
    datePicker: VuePersianDatetimePicker,
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
.form {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 97.5vh;
}
.form-container {
  background-color: rgb(236, 117, 117);
  padding: 2rem;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-content: center;
  height: 100%;
  width: 50%;
}
.elements {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
@media screen and (max-width: 600px) {
  .form-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
}
.lable__form {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
}
.lable__form label {
  margin-bottom: 2rem;
  padding: 0.9rem;
}
.input__form {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
}
.input__form input {
  margin-bottom: 2.1rem;
  outline: none;
  border: none;
  padding: 1rem 1.5rem;
  border-radius: 8px;
}
.img_form {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 100%;
  img {
    width: inherit;
    height: inherit;
  }
}
.btn__primary {
  display: flex;
  justify-content: end;
  align-items: center;
  button {
    outline: none;
    border: none;
    padding: 1rem 1.25rem;
    border-radius: 8px;
    cursor: pointer;
    background-color: rgb(187, 66, 66);
    color: white;
    font-size: 0.85rem;
  }
}
</style>
