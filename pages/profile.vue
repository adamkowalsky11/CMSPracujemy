<template>
    <div>
       
        <card/>
         <v-card>
            <v-card-text>opis </v-card-text>
        </v-card>
        <card/>
    </div>
    
</template>

<script>
import { defineComponent } from '@vue/composition-api'
import card from '~/components/jobComponents/card.vue'
import JobCard from '~/components/jobComponents/jobCard.vue'

export default defineComponent({
  components: { card, JobCard },
    setup() {
        
    },
})
</script>
