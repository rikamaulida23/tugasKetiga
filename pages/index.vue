<template>
  <div class="py-4">
  <div class="container">
  <div class="title border-bottom d-flex align-items-center justify-content-between py-2">
    <h5>Category Resep</h5>
    <div class="d-flex align-items-center">
      <div class="dropdown">
    <button
      class="btn btn-secondary dropdown-toggle"
      type="button"
      id="categoryDropdown"
      data-bs-toggle="dropdown"
      aria-haspopup="true"
      aria-expanded="false"
    >
      Filter by Category
    </button>
    <div class="dropdown-menu" aria-labelledby="categoryDropdown">
      <button
        class="dropdown-item"
        @click="categoryFilter = ''"
      >
      All
      </button>
      <button
        class="dropdown-item"
        @click="categoryFilter = 'Western Food'"
      >
      Western Food
      </button>

      <button
        class="dropdown-item"
        @click="categoryFilter = 'Indonesian Food'"
      >
      Indonesian Food
      </button>

      <button
        class="dropdown-item"
        @click="categoryFilter = 'Korean Food'"
      >
      Korean Food
      </button>
      
    </div>
  </div>
      <div class="d-flex align-item-center justify-content-end w-100">
      <span class="me-2">View As</span>
      <button
      class="btn btn-outline-secondary py-1 px-3"
      @click="isGrid=!isGrid" >
      {{ isGrid ? 'Grid' : 'List' }}
      </button>
    </div>
    </div>
  </div>
  <div class="list-task row">
    <CardItem
    v-for="(task, i) in resultQuery"
    :key="i"
    :task="task"
    :isGrid="isGrid"
    />
  </div>
  <div class="action py-2">
    <a
      v-if="!isCreating" href="#" class="add-button"
      @click="isCreating=!isCreating">Add Resep</a>
    <div v-else class="add-card">
      <div class="card mb-2">
        <div class="card-body d-flex flex-column p-0">
        <input class="form-control border-0 mb-2" placeholder="Title" type="text">
        <textarea
        class="form-control border-0 small" placeholder="Description"
        rows="3"></textarea>
        </div>
      </div>
      <div class="button-wrapper d-flex">
        <button class="btn btn-primary me-2">Save</button>
        <button
        class="btn btn-outline-secondary"
        @click="isCreating =!isCreating">Cancel</button>
      </div>
    </div>
  </div>
  </div>
  </div>
</template>
<script>
import CardItem from "@/components/Card/CardItem.vue"
export default {
  layout (context) {
    return 'custom'
  },
  components: {
    CardItem
  },
  data() {
    return {
      categoryFilter: '',

      isGrid: true,
      
      isCreating: false,
      
      tasks: [
        {
          image: 'https://media.istockphoto.com/id/1310148598/id/foto/dry-aged-barbecue-porterhouse-steak-atau-steak-daging-sapi-t-bone-yang-diiris-dengan-potongan.jpg?s=1024x1024&w=is&k=20&c=nLM6mIFYOcH9Jtt7Depa1cRxixyUv746WUScKtOsqpc=',
          title: 'Steak',
          category: 'Western Food',
          description: 'potongan daging sapi, daging merah, dada ayam, dan ikan. Steik biasanya dimasak dengan dipanggang, meskipun dapat digoreng atau dibroil',
          isDone: false,
        },
        {
          image: 'https://media.istockphoto.com/id/182877803/id/foto/hidangan-indonesia-dengan-tusuk-ayam-sate.jpg?s=1024x1024&w=is&k=20&c=U-YtxVNhNAqPBtJoqs4ZYa8TCbjPtrhJcriZccEh_X0=',
          title: 'Sate Lilit',
          category: 'Indonesian Food',
          description: 'Sate yang terbuat dari daging babi, ikan, ayam, atau daging sapi, kemudian dicampur dengan parutan kelapa, santan, jeruk nipis, bawang merah, dan merica.',
          isDone: false,
        },
        {
          image: 'https://media.istockphoto.com/id/183752521/id/foto/bi-bim-bap.jpg?s=1024x1024&w=is&k=20&c=0AYYvrLMcOyPbP1_Erj2fyipfEEFw-3J2R6oUXZXxEw=',
          title: 'Bimbimbap',
          category: 'Korean Food',
          description: 'Masakan Korea berupa semangkuk nasi putih dengan lauk di atasnya berupa sayur-sayuran, daging sapi, telur, dan saus pedas gochujang.',
          isDone: false,
        },
        
      ]
    }
  },
  computed: {
  resultQuery() {
    if (this.categoryFilter) {
      return this.tasks.filter((item) => item.category === this.categoryFilter);
    } else {
      return this.tasks;
    }
  },
},
}
</script>
<style>
.py-4{
  background-color: gainsboro;
}

.add-button{
  color:black
}

</style>
