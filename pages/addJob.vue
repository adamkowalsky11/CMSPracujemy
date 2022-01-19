<template>
    <div>
        <v-card>
            <v-form>
            <v-row>
                <v-col>

                <v-combobox
          v-model="select"
          :items="items"
          label="Stanowisko"
          multiple
          chips
        >
          <template v-slot:selection="data">
            <v-chip
              :key="JSON.stringify(data.item)"
              v-bind="data.attrs"
              :input-value="data.selected"
              :disabled="data.disabled"
              @click:close="data.parent.selectItem(data.item)"
            >
              <v-avatar
                class="accent white--text"
                left
                v-text="data.item.slice(0, 1).toUpperCase()"
              ></v-avatar>
              {{ data.item }}
            </v-chip>
          </template>
        </v-combobox>
        </v-col>
        </v-row>
                    <v-row>
                        <v-col>
                <v-text-field
                label="Stawka"
                >
          
                </v-text-field>
                </v-col>
            </v-row>
            <v-row>
                <v-col>
                <v-container fluid>
    <v-select
      v-model="value"
      :items="items"
      label="Poziom"
      multiple
    >
      <template v-slot:selection="{ item, index }">
        <v-chip v-if="index === 0">
          <span>{{ item }}</span>
        </v-chip>
        <span
          v-if="index === 1"
          class="grey--text text-caption"
        >
          (+{{ value.length - 1 }} others)
        </span>
      </template>
    </v-select>
  </v-container>
  <v-text-field label="Opis"></v-text-field>
  </v-col>
  </v-row>
            </v-form>
        </v-card>
            <v-btn block>Dodaj ofertę</v-btn>
            

    </div>
    
</template>

<script>
import { defineComponent } from '@vue/composition-api'

export default defineComponent({
    data: () => ({
      items: ['foo', 'bar', 'fizz', 'buzz', 'fizzbuzz', 'foobar'],
      value: ['foo', 'bar', 'fizz'],
    }),
  })
</script>
