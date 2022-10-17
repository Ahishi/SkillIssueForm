<template>
  <div id="FirstFormBody" class="border-2 border-black rounded-md mb-10">
    <h4 class="border-b-2 border-black px-5 py-2.5 font-semibold italic flex"> {{formText}}<p class="ml-2 text-sm my-auto font-normal">(Check all that apply)</p></h4>
    <div class="flex flex-wrap py-2.5">
      <div v-for="(item, key) in formFieldsBody" class="px-5 h-6 my-1">
        <input class="cursor-pointer" type="checkbox" :id="key" :name="item.name" v-model="item.value">
        <label class="cursor-pointer pl-2 font-semibold text-sm inline-block align-top pt-[2px]" :for="key">{{item.name}}</label>
      </div>
      <div class="px-5 flex w-fit my-1">
        <button v-if="!addNew" class="text-sm font-semibold" type="button" @click="addNewBox">Add new</button>
        <div v-if="addNew">
          <input type="checkbox" id="newItem" name="newItem" checked>
          <input class="mx-2 px-2 border-black h-full border-b border-dashed" maxlength="50" v-model="userAddedCheckBox.name" type="text" id="firstOther" name="other">
          <button v-if="addNew" class="bg-purple-800 px-2.5 rounded-full text-sm font-semibold text-white py-0.5" :class="{ 'bg-gray-300 text-gray-400 cursor-default': !userAddedCheckBox.name}" type="button" @click="handleAddNew">Add</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "MultiPartForm",

  props: {
    formFieldsBody: [],
    formText: String
  },

  data() {
    return {
      addNew: false,
      addNewInvalid: false,
      userAddedCheckBox: {name: "", value: true},
    }
  },

  methods: {

    addNewBox(){
      this.addNew = !this.addNew;
    },

    handleAddNew(){
      if(this.userAddedCheckBox.name !== ""){
        this.$emit('addToListEvent', this.userAddedCheckBox);
        this.userAddedCheckBox = {name: "", value: true};
        this.addNew = false;
      } else {
        this.addNewInvalid = true;
      }
    }
  }
}
</script>