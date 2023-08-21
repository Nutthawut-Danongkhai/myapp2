<template>
  <div class="container">
  <img :src="picture" :width="size" :height="size" />
  <p>ชื่อ-นามสกุล : {{ getFullname() }}</p>
  <p>นามสกุล : {{ age }}</p>
  <button @clik="toggleVisible">{{ isVisible? "ซ่อน" : "แสดง" }}รายละเอียด</button>
 <div v-show="toggleVisible">
  <p>ที่อยู่ : <span v-html="address"></span></p>
  <p v-if></p>
  </div> 
  </div>