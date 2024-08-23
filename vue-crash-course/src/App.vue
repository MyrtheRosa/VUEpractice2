<script>
export default {
  data() {
    return {
      name: 'Rosa',
      status: 'active',
      tasks: ['Task one', 'Task two', 'Task three'],
      link: 'https://google.com',
    };
  },
  methods: {
    toggleStatus(){
      if(this.status === 'active'){
        this.status = 'pending';
      } else if(this.status === 'pending'){
        this.status = 'inactive';
      } else{
        this.status = 'active';
      }
    }
  }
};
</script>

<template>
  <h1>{{ name }}</h1>
  <p v-if="status === 'active'">User is active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else-if="status === ''">Status is empty</p>
  <p v-else>User is inactive</p>

  <h3>Tasks: </h3>
  <ul>
    <li v-for="task in tasks" :key="task"> {{ task }} </li>
  </ul>
  <!-- Twee opties. optie 1; 
   <a v-bind:href="link">Click for Google</a> 
   Optie 2--> <a :href="link">Click for Google</a>
    <br/>
   <!-- <button v-on:click="toggleStatus">Change Status</button> -->
   <button @click ="toggleStatus">Change Status</button>

</template>
