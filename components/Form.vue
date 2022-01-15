<template>
  <form class="bg-white shadow-md rounded px-8 pt-6 pb-8 mb-4">
    <div class="mb-4">
      <label class="block text-gray-700 text-sm font-bold mb-2" for="name">
        Name
      </label>
      <input
        class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
        id="name"
        type="text"
        placeholder="name"
        ref="name"
      />
    </div>
    <div class="mb-6">
      <label class="block text-gray-700 text-sm font-bold mb-2" for="feedback">
        Feedback
      </label>
      <input
        class="shadow appearance-none border rounded w-full py-2 px-3 text-gray-700 leading-tight focus:outline-none focus:shadow-outline"
        id="feedback"
        type="text"
        placeholder="feedback"
        ref="feedback"
      />
    </div>
    <div class="flex items-center justify-between">
      <button
        class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded focus:outline-none focus:shadow-outline"
        type="button"
        @click.prevent="getFormValues()"
      >
        Submit
      </button>
    </div>
  </form>
</template>

<script>
export default {
  data() {
    return {
      name: "",
      feedback: "",
      videoEnded: "",
    };
  },
  methods: {
    getFormValues() {
      alert(`Feedback received successfully!`);
      console.log(this.$refs.name.value);
      console.log(this.$refs.feedback.value);
    },
  },
};
</script>

<style></style>
