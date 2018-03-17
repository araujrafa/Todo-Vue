<template>
  <div class="ui centered card">
    <div class="content" v-show="!isEdition">
      <div class="header">
        {{ todo.title }}
      </div>
      <div class="meta">
        {{ todo.project }}
      </div>
      <div class="extra content">
        <span class="right floated edit icon" v-on:click="showForm">
          <i class="edit icon"></i>
        </span>
      </div>
    </div>
    <div class="content" v-show="isEdition">
      <div class='ui form'>
        <div class="field">
          <label>Titulo</label>
          <input type="text" v-model="todo.title">
        </div>
        <div class="field">
          <label>Projeto</label>
          <input type="text" v-model="todo.project">
        </div>
        <div class='ui two button attached buttons'>
          <button class='ui basic blue button' v-on:click="hideForm">
            Close X
          </button>
        </div>
      </div>
    </div>
    <div class='ui bottom attached green basic button' v-show="!isEditing &&todo.done" disabled>
        Completada
    </div>
    <div class='ui bottom attached red basic button' v-show="!isEditing && !todo.done">
        Pendente
    </div>
  </div>
</template>

<script>
export default {
  props: ['todo'],
  data () {
    return {
      isEdition: false
    }
  },
  methods: {
    showForm () {
      this.isEdition = true
    },
    hideForm () {
      this.isEdition = false
    }
  }
}
</script>
