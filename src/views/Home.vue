<template>
<b-container>
  <b-row align-v="center">
    <report-card v-for="report in reports" :key="report.id" :title="report.title" :description="report.description" :author="report.author" ></report-card>
  </b-row>
</b-container>
</template>

<script>
// @ is an alias to /src
import ReportCard from '@/components/ReportCard.vue'


export default {
  name: "Home",
  components: { "report-card": ReportCard },
  mounted(){
    this.fetchData();

  },
  data(){
    return {
      reports: []
    }
  },
  methods: {
    // should be some error handling and might switch to axios
    async fetchData(){
      const res = await fetch("reports.json");
      const val = await res.json();
      this.reports = val;
      console.log(val);

    }
  }
};
</script>
