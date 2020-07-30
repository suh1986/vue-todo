<template>
  <div>
    <div  @click="isOpen=true" class="app-button">
      Create
    </div>
    <div class="modal" :class="{'is-active': isOpen}">
        <div class="modal-content">
          <span @click="isOpen=false" class="close">&times;</span>
          <form class="app-form">
            <div class="form-control">
              <label class="label">Title</label>
              <input 
              v-model="form.title" 
              class="form-input" 
              type="text">
            </div>
            <div class="form-control">
              <label class="label">Description</label>
              <input
              v-model="form.description" 
              class="form-input" 
              type="text">
            </div>
            <button
            @click="createToDo" 
            type="button" 
            class="app-button is-primary">
              Confirm
            </button>
          </form>
        </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      isOpen:false,
      form: {
        title: "",
        description: ""
      }

    }
  },
  methods: {
    createToDo() {
      console.log(this.form)
    }
  }
}
</script>
<style scoped lang="scss">
  .app-form {
    .label {
      display: block;
      font-size: 18px;
      font-weight: bold
    }
    .form-input {
      padding: 10px;
      font-size: 17px;
    }
    .form-input {
      padding: 10px;
      font-size: 17px;
    }
    .form-control {
      margin-bottom: 10px
    }
  }
  .modal {
    display: none;
    position: fixed; // stay in place
    z-index: 9999;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    overflow: auto; // enable scroll if needed
    background-color: rgba(0, 0, 0, 0.4);
    &.is-active {
      display: block;
    }
  }
  .modal-content {
    background-color: #fefefe;
    margin: 15% auto;
    padding: 20px;
    border: 1px solid #888;
    width: 80%;
  }
  .close {
    color: #aaa;
    float: right;
    font-size: 28px;
    font-weight: bold;
    line-height: 8px;
    &:hover {
      cursor: pointer;
    }
  }
  .app-button {
    font-size: 20px;
    padding: 10px;
    margin: 10px;
    border-radius: 5px;
    background-color: #795899;
    color: white;
    font-weight: bold;

     &:hover {
      cursor: pointer;
    }
    &-create-btn-container {
      margin: 10px;
    }
  }
</style>