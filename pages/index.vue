<template>
  <div class="center">
    <div class="contacts">
      <h2 style="text-decoration: underline; margin-bottom: 3rem">
        Chats
      </h2>
      <div class="contact">
        <li v-for="session in chatSessions" @click="getChat(session.sessionID)">
          <div class="name">
            Session ID
          </div>
          <div class="message">
            {{ session.sessionID }}
          </div>
        </li>
      </div>
    </div>
    <div class="chat">
      <div class='contact bar'>
        <div class='pic helpdesk'></div>
        <div class='name'>Help Desk</div>
      </div>
      <div class="messages" id="chat">
        <li v-for="message in messages">
          <b>{{ message.sender.toUpperCase() }}:</b>
          <div class='message'>{{ message.message }}</div>
        </li>
      </div>
      <div class="input">
        <input placeholder='Type your message here!' v-model="text" />
        <svg xmlns='http://www.w3.org/2000/svg' width='26' height='26' fill='currentColor' class='bi bi-send'
          viewBox='0 0 16 16' @click="sendMessage()">
          <path
            d='M15.854.146a.5.5 0 0 1 .11.54l-5.819 14.547a.75.75 0 0 1-1.329.124l-3.178-4.995L.643 7.184a.75.75 0 0 1 .124-1.33L15.314.037a.5.5 0 0 1 .54.11ZM6.636 10.07l2.761 4.338L14.13 2.576 6.636 10.07Zm6.787-8.201L1.591 6.602l4.339 2.76 7.494-7.493Z' />
        </svg>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'IndexPage',
  data() {
    return {
      chatSessions: [],
      sessionID: '',
      messages: [],
    }
  },
  methods: {},
}
</script>

<style>
@import '../main.css';
</style>