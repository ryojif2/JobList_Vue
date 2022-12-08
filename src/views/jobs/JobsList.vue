<template>
  <h1>Jobs</h1>
  <div v-if="jobs.length">
    <div v-for="job in jobs" :key="job.id">
      <router-link :to="{ name: 'jobDetails', params: { id: job.id } }">
        <h2>{{ job.title }}</h2>
      </router-link>
    </div>
  </div>
  <div v-else>
    <h2>Loading Jobs...</h2>
  </div>
</template>

<script>
export default {
  data() {
    return {
      jobs: [
        { title: "UX Designer", id: 1, details: "abc" },
        { title: "Web Developer", id: 2, details: "def" },
        { title: "Vue Developer", id: 3, details: "ghi" },
      ],
    };
  },
  mounted() {
    fetch("https://")
      .then((data) => data.json())
      .then((data) => (this.jobs = data))
      .catch((err) => console.log(err.message));
  },
};
</script>

<style></style>
