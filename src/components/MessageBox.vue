<template>
  <div class="messageBox-wrapper">
    <div class="messageBox">
      <ul class="messageList">
        <li v-for="item in messageList" :key="item.id">
          {{ item.message }}
        </li>
      </ul>
      <textarea v-model="messageValue" style="resize: none"></textarea>
      <button @click="saveMessage">Wyslij</button>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const messageValue = ref("");
    const messageList = ref([
      {
        id: "",
        message: "",
      },
    ]);

    const saveMessage = () => {
      console.log("Tu masz wiadomość:", messageValue.value);

      const newMessage = {
        id: Date.now(),
        message: messageValue.value,
      };
      messageList.value.push(newMessage);

      console.log("Obiekt wiadomości:", messageList);
    };

    return {
      messageValue,
      saveMessage,
      messageList,
    };
  },
};
</script>
<style scoped></style>
