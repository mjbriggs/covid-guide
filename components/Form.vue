<template>
  <nb-container>
    <nb-content>
        <nb-content horizontal>
          <nb-text>gender</nb-text>
          <nb-button style='padding' first :active="isMale" :on-press="clickMale">
            <nb-text>Male</nb-text>
          </nb-button>
          <nb-button :active="isFemale" :on-press="clickFemale">
            <nb-text>Female</nb-text>
          </nb-button>
          <nb-button last :active="isOther" :on-press="clickOther">
            <nb-text>Other</nb-text>
          </nb-button>
        </nb-content>
        
        <!-- <nb-form>
          <nb-item floatingLabel>
            <nb-label>Age</nb-label>
            <nb-input v-model='age'/>
          </nb-item>
          <nb-item floatingLabel>
            <nb-label>City</nb-label>
            <nb-input v-model='city'/>
          </nb-item>
          <nb-item floatingLabel>
            <nb-label>State</nb-label>
            <nb-input v-model='state'/>
          </nb-item>
      </nb-form> -->
    </nb-content>
  </nb-container>
</template>

<script>
import React from 'react';
import { Picker, Icon, Toast } from 'native-base';
export default {
  components: { Item: Picker.Item },
  data: function() {
    return {
      gender: '',
      age: 0,
      city: '',
      state: '',
      isMale: false,
      isFemale: false,
      isOther: false
    };
  },
  methods: {
    clickMale: function() {
      console.log("clickMale");
      this.isMale = !this.isMale;
      this.isFemale = false;
      this.isOther = false;   
      this.gender = "Male";
    },
    clickFemale: function() {
      console.log("clickFemale");
      this.isMale = false;
      this.isFemale = !this.isFemale;
      this.isOther = false;
      this.gender = "Female";
    },
    clickOther: function() {
      console.log("clickOther");
      this.isMale = false;
      this.isFemale = false;
      this.isOther = !this.isOther;  
      this.gender = "Other"; 
    },
    didSomething: function() {
      alert('age : ' + this.age);
    },
    onGenderValueChange: function(value) {
      console.log(this.gender);
      console.log(this.age);
      console.log(this.city);
      console.log(this.state);
      this.gender = value;
    },
    getIosIcon: function() {
      return <Icon name='ios-arrow-down' />;
    }
  }
};
</script>

<style>
.genderBtn {
  padding: 10 10 10 10;
  color: red;
}
.add-btn {
  height: 35px;
  width: 100px;
  background-color: #FFCE00;
  justify-content: center;
  align-items: center;
}
</style>