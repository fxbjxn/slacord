<template>
  <div class="messageBox-wrapper">
    <ul class="messageList">
      <li v-for="item in messageList" :key="item.id">
        {{ item.message }}
      </li>
    </ul>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  props: ["messageList"],
};
</script>
