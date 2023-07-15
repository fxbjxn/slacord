<template>
  <div class="messageBox-wrapper">
    <div class="messageBox">
      <v-list class="messageList" lines="two">
        <v-list-item
          v-for="item in messageList"
          :key="item.id"
          :title="item.title"
          subtitle="Albert"
        >
          {{ item.message }}</v-list-item
        >
      </v-list>
      <!-- <li v-for="item in messageList" :key="item.id">
          {{ item.message }}
        </li>
      </ul> -->
      <div class="messageSend">
        <v-textarea
          class="textArea"
          v-model="messageValue"
          clearable
          counter
          label="Send a message"
          prepend-icon="$vuetify"
          variant="underlined"
          no-resize
        ></v-textarea>
        <v-btn prepend-icon="$vuetify" variant="tonal" @click="saveMessage"
          >Wyslij</v-btn
        >
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  setup() {
    const messageValue = ref("");
    const messageList = ref([
      // {
      //   id: "",
      //   message: "Hello",
      // },
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
<style scoped>
.messageList {
  background-color: yellow;
  color: black;
  min-height: 30px;
  max-height: 300px;
  overflow-y: scroll;
}

.messageList {
  min-width: 1250px;
}
.messageSend {
  min-width: 400px;
  max-width: 600px;
}
.textArea {
  margin-top: 10px;
  resize: none;
  font-size: 1.2rem;
}
</style>
