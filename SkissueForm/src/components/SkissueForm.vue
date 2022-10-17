<template>
  <form action="" class="2xl:w-3/4 mx-auto">

    <div id="FormHeader">
      <h1 class="text-3xl text-center mb-10 font-semibold italic">Skill Issue Assesment Form</h1>
      <div class="flex mb-5 text-sm font-semibold">
        <div>
          <label>Steam name:</label>
          <input class="mx-2 px-2 border-black h-full border-b border-dashed" placeholder="Steam name" maxlength="50" type="text" id="Name" name="name">
        </div>
        <div class="block ml-auto flex">
          <div class="ml-5">
            <label>Time:</label>
            <input class="mx-2 px-2 border-black h-full border-b border-dashed" placeholder="Time" maxlength="50" type="text" id="Time" name="Time">
          </div>
          <div class="ml-5">
            <label>Date:</label>
            <input class="mx-2 px-2 border-black h-full border-b border-dashed" type="date" id="Date" name="Date">
          </div>
        </div>
      </div>
    </div>

    <MultiPartForm :form-fields-body="formFields.firstBody" form-text="What was going through your head upon having a skill issue?" @addToListEvent="callback"/>

    <ListPartForm :form-fields-body="formFields.secondBody" form-text="What initially caused your skill issue to occur?"/>

    <MultiPartForm :form-fields-body="formFields.thirdBody" form-text="What have you tried so far to remedy your skill issue?" @addToListEvent="callback"/>

    <div class="flex">
      <button class="font-semibold bg-purple-800 rounded-full px-4 py-2 text-white transition ease-in-out hover:bg-purple-900 duration-200" type="submit" value="Submit">Save form</button>
      <button class="px-4 py-2" type="button">Cancel</button>
      <div class="block ml-auto">
        <h4 class="font-semibold text-sm my-auto text-center">Visibility</h4>
        <div class="my-auto">
          <button type="button" @click="visibilityPrivate = true" class="border-r border-gray-300 w-[67px] px-2.5 text-sm" :class="{'font-bold': visibilityPrivate}">Private</button>
          <button type="button" @click="visibilityPrivate = false"  class="px-2.5 w-[67px] text-sm" :class="{'font-bold': !visibilityPrivate}">Group</button>
        </div>
      </div>
    </div>
  </form>
</template>

<script>
import MultiPartForm from "./MultiPartForm.vue";
import ListPartForm from "./ListPartForm.vue";

export default {
  name: "SkissueForm",
  components: {ListPartForm, MultiPartForm},

  data() {
    return {
      visibilityPrivate: false,

      formFields: {
        firstBody: [ {name: "Test1", value: false}, {name: "Test2", value: false}, {name: "Test3", value: false}, {name: "Test4", value: false}, {name: "Test4", value: false}, {name: "Test4", value: false}, {name: "Test5", value: false}, {name: "Test1", value: false}, {name: "Test2", value: false}, {name: "Test3", value: false}, {name: "Test4", value: false}, {name: "Test5", value: false}, {name: "Test1", value: false}, {name: "Test2", value: false}, {name: "Test3", value: false}, {name: "Test4", value: false}, {name: "Test5", value: false}, {name: "Test1", value: false}, {name: "Test2", value: false}, {name: "Test3", value: false}, {name: "Test4", value: false}, {name: "Test5", value: false}, {name: "Test1", value: false}, {name: "Test2", value: false}, {name: "Test3", value: false}, {name: "Test4", value: false}, {name: "Test5", value: false} ],
        secondBody: [ {name: "Test1", value: false}, {name: "Test2", value: false}, {name: "Test3", value: false}, {name: "Test4", value: false}, {name: "Test5", value: false} ],
        thirdBody: [ {name: "Test1", value: false}, {name: "Test2", value: false}, {name: "Test3", value: false}, {name: "Test4", value: false}, {name: "Test5", value: false} ],
      }
    }
  },

  methods: {
    callback(object){
      this.formFields.firstBody.push(object);
    }
  }
}
</script>