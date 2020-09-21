<template>
  <div>
       <b-col >
      <b-card
      :title="title"
      img-src="https://i.picsum.photos/id/1025/4951/3301.jpg?hmac=_aGh5AtoOChip_iaMo8ZvvytfEojcgqbCH7dzaz-H8Y"
      img-alt="report-info"
      img-top
      tag="lending"
      style="max-width:20 rem"
      class="mb-2"
      >
      <!-- <b-card-text>{{description}}</b-card-text> -->
    <b-list-group flush>
      <b-list-group-item class="h2" :description ="description">{{description}}</b-list-group-item>
      <b-list-group-item class="h5" :author ="author"><strong>{{author}}</strong></b-list-group-item>
    </b-list-group>
        <b-button variant="primary">Apply</b-button>
      </b-card>
    </b-col>





  </div>
  
</template>

<script>
  export default {
    props: ['title', 'description', 'author']
    
  }
</script>

<style lang="scss" scoped>

</style>