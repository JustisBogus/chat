<template lang="html">

<div class="chat-log">

    <chat-message v-for="message in messages" v-bind:message="message" v-bind:key="messages.message"></chat-message>
    <div class="empty" v-show="messages.leght === 0">
        Say Hi!
    </div>
   
    </div>
  
</template>

<script>
export default { 

    props: ['messages']
}
</script>
 
<style lang="css">

.chat-log .chat-message:nth-child(even) {
    background-color: #ccc;
}

.empty {
    padding: 1rem;
    text-align: center;
}


</style>
 