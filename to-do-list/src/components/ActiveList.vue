<template>
  <ul class="list-group mb-0">
    <li
      class="list-group-item d-flex align-items-center border-0 mb-2 rounded"
      style="background-color: #f4f6f7"
    >
      <input class="form-check-input me-1" type="checkbox" value="" checked />
      <p class="m-2">{{ todo.task }}</p>
    </li>
  </ul>
</template>

<script>
export default {
  name: "ActiveList",
  props: {
    todo: {
      type: Object,
      required: true,
    },
  },
};
</script>
