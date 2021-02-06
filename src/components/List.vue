<template>
  <div>
    <ul>
      <li v-bind:key="record._id" v-for="record in records" class="record_li">
        <h3>{{ record.title }}</h3>
        <p class="record_info">Cost: {{ record.cost }}</p>
        <p class="record_info">
          <a v-bind:href="record.url" rel="noopener noreferrer" target="_blank"
            >Link</a
          >
        </p>
      </li>
    </ul>
  </div>
</template>

<script>
// import TodoItem from "./TodoItem";
export default {
  name: "List",
  //   components: {
  //     TodoItem,
  //   },
  props: ["records"],
};
</script>

<style scoped>
.record_li {
  display: flex;
  align-items: center;
  text-align: left;
}
.record_info {
  margin-left: 1rem;
}
</style>