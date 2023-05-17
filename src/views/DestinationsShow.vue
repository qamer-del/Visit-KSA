<template>
  <div>
    <section  class="destination">
        <h2>{{ destination.name }}</h2>
    
    <div class="destination-details">
      <img :src="`/images/${destination.image}`" :alt="destination.name" />
      <p>{{ destination.description }}</p>
    </div>
  </section>
  <section class="experiences">
    <h1>Top Experiences name {{ destination.name }}</h1>
     <GoBack/>
    <div class="cards">
      <router-link :to="{ name: 'experiences.show', params:{experienceSlug:experiences.slug} }"  v-for="experiences in destination.experiences"
        :key="experiences.slug">
        <ExperiencesCrad
        
        :experiences="experiences" 
        />
      </router-link>
    </div>
    <router-view/>
  </section>
  </div>
  </template>
  <script>
    import sourceData from '@/data.json';
    import ExperiencesCrad from '@/components/ExperiencesCrad.vue';
    import GoBack  from '@/components/GoBack.vue';
  export default{
    components:{ExperiencesCrad , GoBack},
    props:{
      id:{
        type: Number,
        required: true, 
      }
    },
    computed:{
       destination(){
        return sourceData.destinations.find(destination => destination.id === this.id)
       }
    }
  }
  </script>
  