 <template lang="html">

    <div class="chat-composer">

        <input type="text" placeholder="Your Message" v-model="messageText" v-on:keyup.enter="sendMessage">
        <button class="btn btn-primary" @click="sendMessage">Send</button>

        </div>

</template>

<script>

export default {

    data() {

        return {

            messageText: ''
        }
    },

    methods: {
        sendMessage() {
            this.$emit('messagesent', 
            {
             message: this.messageText,
             user: {
                 name: $('.navbar-right .dropdown-toggle').text()
                 
             }
              });
            this.messageText = '';
        }
    }

}
 
</script>

<style>

.chat-composer {
    display:flex;
}

.chat-composer input {
    flex: 1 auto;
}

.chat-composer button {
            width:100px;
            height:35px;
            top:15px;
            right:15px;
            z-index:2;
            border-radius:5px;
            border-color:white;
            background:#ccc;
  
            box-shadow:none;
            outline:none;
            cursor:pointer;
}


</style>