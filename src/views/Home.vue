<template>
<b-container>
  <b-row align-v="center">
    <report-card v-for="report in reports" :key="report.id" :title="report.title" :description="report.description" :author="report.author" ></report-card>
  </b-row>
</b-container>
</template>

<script>
// @ is an alias to /src
import ReportCard from '@/components/ReportCard.vue';
import axios from 'axios';

var myConfig = {
  mode: 'no-cors',
  headers: {
    'Access-Control-Allow-Origin': '*',
    Authorization: "Bearer " + "eyJhbGciOiJodHRwOi8vd3d3LnczLm9yZy8yMDAxLzA0L3htbGRzaWctbW9yZSNobWFjLXNoYTI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE2MDA3ODYyNTEsImlzcyI6Imhvd2FyZC5pbmR1c3RyaWVzIiwiYXVkIjoicmVhZGVycyJ9.jNLGjlcRPrqttMpjG80ZtJFSpR3uYfMWQ0yVZSEv9DA",
    'Content-Type':'application/json'
  },
  credentials: 'same-origin'
 
}

export default {
  name: "Home",
  components: { "report-card": ReportCard },
  created(){
       axios
          .get('https://localhost:44366/api/quotes', myConfig)
          .then(res=> this.reports =  res.data)
          .catch(error => console.log(error))
  },
  mounted(){
          //   axios
          // .get('https://localhost:44366/api/quotes', myConfig)
          // .then(res=> this.reports =  res.data)
          // .catch(error => console.log(error))
  },
  data(){
    return {
      reports: []
    }
  },
  methods: {
    // should be some error handling and might switch to axios
    // async fetchData(){
    //   const res = await fetch("reports.json");
    //   const val = await res.json();
    //   this.reports = val;
    //   console.log(val);
    // }
    // let's try this with axios

  }
};
</script>
