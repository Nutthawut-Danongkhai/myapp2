<template>
  <div class="container">
  <img :src="picture" :width="size" :height="size" />
  <form @submit.prevent="submitForm">
    กรอกชื่อเล่น <input type="text" ref="nicknameEl">
    <input type="submit" value="บันทึก">
  </form>
  <p>ชื่อ-นามสกุล : {{ getFullname() }}</p>
  <p>ชื่อเล่น : {{ nickname }}</p>
  <p>อายุ : {{ age }}</p>
  <button @click="toggleVisible">{{ isVisible? "ซ่อน" : "แสดง" }}รายละเอียด</button>
 <div v-show="isVisible">
  <p>ที่อยู่ : <span v-html="address"></span></p>
  <p v-if="hobby.length === 0">ไม่มีงานอดิเรก</p>
  <div v-else>
    <p>งานอดิเรก :</p>
    <ul>
      <li v-for="items in hobby">{{ items }}</li>
    </ul>
  </div>
  <p>ข้อมูลพื้นฐาน :</p>
  <ul>
    <li>เพศ : {{ general.gender }}</li>
    <li>น้ำหนัก : {{ general.weight }}</li>
    <li>ส่วนสูง : {{ general.height }}</li>
    <li>โรคประจำตัว : {{ general.status }}</li>
  </ul>
  </div> 
  </div>
</template>
  <script>
  export default {
    data() {
      return{
        firstname: "Nutthawut",
        lastname: "Danongkhai",
        nickname :"",
        age: 18,
        address: "<i>Chonburi</i>",
        picture: "https://lh3.googleusercontent.com/a/AAcHTtcjRx5o9w81peeW9hbeSQGo1oWLXvGhcVeWl-jZZLy7Irw=s260-c-no",
        size: 150,
        hobby: ["ทำสวน", "ดำน้ำ", "เล่นเกม"],
        general: { gender: "ชาย", weight: 50.7, height: 162, status:false},
        isVisible: false,
      };
    },
    methods: {
      getFullname() {
        return `${this.firstname} ${this.lastname}`;
      },
      toggleVisible(){
        this.isVisible = !this.isVisible
      },
      submitForm(){
        this.nickname = this.$refs.nicknameEl.value
      }
    },
  };
  </script>
