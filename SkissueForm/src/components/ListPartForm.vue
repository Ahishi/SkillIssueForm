<template>
  <div id="SecondFormBody" class="border-2 border-black rounded-md mb-10">
    <h4 class="border-b-2 border-black px-5 py-2.5 font-semibold italic flex"> {{formText}} <p class="ml-2 text-sm my-auto font-normal">(Check all that apply)</p></h4>
    <ul class="py-2.5">
      <li v-for="(item, key) in formFieldsBody" class="px-5 h-6 my-1">
        <input class="cursor-pointer" type="checkbox" :id="item.name+key" :name="item.name" v-model="item.value">
        <label class="cursor-pointer pl-2 font-semibold text-sm inline-block align-top pt-[2px]" :for="item.name+key">{{item.name}}</label>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "ListPartForm",

  props: {
    formFieldsBody: [],
    formText: String
  },
}
</script>