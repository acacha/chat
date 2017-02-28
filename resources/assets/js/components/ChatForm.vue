<template>
    <form action="#" method="post">
        <div class="input-group">
            <input type="text" name="message" placeholder="Type Message ..." class="form-control" v-model="newMessage" @keyup.enter="sendMessage">
            <span class="input-group-btn">
                <button type="submit" class="btn btn-primary btn-flat" @click="sendMessage">Send</button>
            </span>
        </div>
    </form>
</template>

<script>
    export default {
      props: ['user'],
      data() {
            return {
                newMessage: ''
            }
        },
      methods: {
            sendMessage() {
                this.$emit('messageSent', {
                    user: this.user,
                    message: this.newMessage
                });

                this.newMessage = ''
            }
      }
    }
</script>
