<template>
  <div class="settings-page">
    <div class="container page">
      <div class="row">
        <div class="col-md-12">
          <h1 class="text-xs-center">{{ message }}</h1>
          <span v-once>This will never change: {{ message }}</span>

          <span v-bind:title="bindmessage">
            Hover your mouse over me for a few seconds
            to see my dynamically bound title!
          </span>
          <hr/>
          <span v-if="react">I am a React Expert.</span>
          <span v-if="!react">I am a Vue Expert.</span>
          <hr />

          <ol>
            <li v-for="todo in todos">
              {{ todo.text }}
            </li>
          </ol>

          <hr/>
          <button v-on:click="reverseMessage">Reverse Message</button>

          <hr/>
          <input v-model="message">

          <hr/>
          <ol>
            <li v-for="grocery in groceryList">
              {{ grocery.text }}
            </li>
          </ol>
          <hr/>

          <button v-bind:disabled="isButtonDisabled">Button</button>

          <hr/>


        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "RwvTest",
  data: function(){
    return {
      message: 'Hello Vue!',
      bindmessage: 'You loaded this page on ' + new Date().toLocaleString(),
      react: false,
      todos: [
        { text: 'Learn JavaScript' },
        { text: 'Learn Vue' },
        { text: 'Build something awesome' }
      ],
      groceryList: [
        { id: 0, text: 'Vegetables' },
        { id: 1, text: 'Cheese' },
        { id: 2, text: 'Whatever else humans are supposed to eat' }
      ],
      isButtonDisabled: true
    }
  },
  methods: {
    reverseMessage: function () {
      console.log('Hello Eugene: ' + new Date())
      this.message = this.message.split('').reverse().join('')
    }
  }
}
</script>