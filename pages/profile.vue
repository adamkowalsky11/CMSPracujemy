<template>
    <div>
       
       <profile-card/>

        <card/>
    </div>
    
</template>

<script>
import { defineComponent } from '@vue/composition-api'
import profileCard from '~/components/jobComponents/profileCard.vue'
import JobCard from '~/components/jobComponents/jobCard.vue'
import card from '~/components/jobComponents/card.vue'


export default defineComponent({
  components: { profileCard, JobCard, card },
    setup() {
        
    },
})
</script>
