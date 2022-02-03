<template>
  <div id="app">
    <div id="example-6">
      <input @keyup.ctrl="say('복사')">
      <button @click.ctrl="say('컨트롤키 눌림')">Ctrl-1</button>
      <button @click.ctrl.exact="say('컨트롤키만 눌림')">Ctrl-2</button>
    </div>
    <div id="example-5">
      <a @click.stop="doThis">클릭 이벤트 전파 중단</a>
    </div>
    <div id="example-4">
      <button @click="warn('Form cannot be submitted yet.', $event)">Submit</button>
      <input @keyup.enter="say('엔터')">
    </div>
    <div id="example-3">
      <button v-on:click="say('hi')">Say hi</button>
      <button @click="say('what')">Say what</button>
    </div>
    <div id="example-2">
      <button v-on:click="greet">Greet</button>
    </div>
    <div id="example-1">
      <button @click="counter++">Add 1</button>
      <button v-on:click="counter++">Add 1</button>
      <p>위 버튼을 클릭한 횟수는 {{ counter }} 번 입니다.</p>
    </div>
  </div>
</template>

<script>
export default {
  components: {
  },
  data() {
    return {
      counter: 0,
    }
  },
  methods: {
    greet: function(event) {
      alert('hi... 당신은 ' + this.counter + '번 클릭하셨습니다!')
      if(event) {
        alert(event.target.tagName)
      }
    },
    say: function(msg) {
      alert(msg)
    },
    warn: function(message, event) {
      if(event) event.preventDefault()
      alert(message)
    },
    doThis() {
      alert('a태그 이동 안함')
    }
  },
}
</script>

<style>

</style>
