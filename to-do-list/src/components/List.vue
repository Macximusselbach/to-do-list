<template>
  <div class="body">
    <div class="input">
      <input v-model="itemToAdd" type="text" placeholder="Digite o item" />
      <button @click="addItem" type="button">Adicionar</button>
    </div>
    <div class="items-list">
        <h1>Lista</h1>
      <ul>
        <li v-for="item in items" :key="item">
          {{ item }}
          <button @click="deleteItem(item)" type="button" class="btn-delete">Deletar</button>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "List",
  data: function () {
    return {
      items: [],
      itemToAdd: "",
      validation: false,
    };
  },
  methods: {
    addItem: function () {
      this.validateItemToAdd();

      if (this.validation == true) {
        this.items.push(this.itemToAdd);
        this.itemToAdd = "";
      }
    },
    deleteItem: function (item) {
      const indexToDelete = this.items.indexOf(item);

      if (indexToDelete != -1) {
        this.items.splice(indexToDelete, 1);
      }
    },
    validateItemToAdd: function () {
      if (this.itemToAdd != "") {
        this.validation = true;
      } else {
        this.validation = false;
      }
    },
  },
};
</script>

<style>

    .body {
        align-items: center;
    }
    .items-list {
        margin-left: 530px;
        max-width: 200px;
    }

    ul li {
        margin-top: 10px;
    }

    .btn-delete {
        margin-left: 10px
    }
</style>