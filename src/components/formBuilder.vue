<template>
  <div class="content">
    <div class="form">
      <div class="form-container">
        <div class="total_form">
          <div class="lable_form">
            <label for="password">Password:</label>
            <label for="email">Email:</label>
            <label for="phone_number">PhoneNumber:</label>
            <label for="gender">GenderType:</label>
            <label for="postal-code">PostalCode:</label>
            <label for="address">Address:</label>
            <label for="birth-date">BirthDate:</label>
          </div>
          <div class="input_form">
            <input type="password" id="password" />
            <input type="text" id="email" />
            <input type="text" id="phone_number" />
            <div class="checkbox_form">
              <div class="famel">
                <label for="female">female</label>
                <input type="checkbox" class="checkbox" id="female" />
              </div>
              <div>
                <label for="male">male</label>
                <input type="checkbox" class="checkbox" id="male" />
              </div>
            </div>
            <input type="text" id="post-code" />
            <input type="text" id="address" />
            <input type="text" id="birth-date" />
          </div>
        </div>
        <div class="img_form">
          <img src="../assets/images/1.png" alt="" />
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "formBuilder",
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
.form-container {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-content: center;
  height: 100%;
}
@media screen and (max-width: 600px) {
  .form-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }
}
.total_form {
  display: flex;
  align-content: center;
  justify-content: space-between;
}
.lable_form {
  width: auto;
  background-color: rgb(185, 14, 185);
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  
}
.input_form {
  width: auto;
  background-color: rgb(17, 185, 177);
  display: flex;
  flex-direction: column;
  align-items: flex-start;
 
}
.lable_form label {
  border-radius: 8px;
  background-color: #f1bdf1;
}
.input_form input {
  outline: none;
  border: none;
  border-radius: 8px;
  background-color: burlywood;
}
.img_form {
  background-color: rgb(174, 185, 17);
}
.checkbox_form {
  display: flex;
  justify-content: space-around;
  align-items: center;
  width: 100%;
}
#male,
#female {
  margin-left: 0.5rem;
}
.checkbox:hover input ~ .checkmark {
  background-color: #c095c0;
}
</style>
