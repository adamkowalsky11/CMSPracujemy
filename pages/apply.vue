<template>
<div>
    <v-header>
        Formularz zgłoszeniowy
    </v-header>
    <card/>
    <job-form/>
</div>
</template>
<script>
import { defineComponent } from '@vue/composition-api'
import card from '~/components/jobComponents/card.vue'
import jobForm from '~/components/jobComponents/jobForm.vue'


export default defineComponent({
  components: { card, jobForm },
    setup() {
        
    },
})
</script>
