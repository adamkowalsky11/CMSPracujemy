<template>
    <div>
        <v-row>
            <v-col>
            <jobCard/>
            </v-col>
        </v-row>
        <v-row>
            <v-col>
        <descriptionCard/>
            </v-col>
        </v-row>
        <v-row>
            <v-col>
        <v-btn block>
            Aplikuj
        </v-btn>
            </v-col>
        </v-row>

    </div>
</template>

<script>
import Card from '~/components/jobComponents/card.vue'

import { defineComponent } from '@vue/composition-api'
import jobCard from '~/components/jobComponents/jobCard.vue'

export default defineComponent({
  components: { jobCard },
    setup() {
        
    },
})
</script>
