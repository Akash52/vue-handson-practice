<template>
  <div>
    <h1>Create an event</h1>
    <form @submit.prevent="sendForm">
      <BaseSelect
        :options="categories"
        v-model="event.category"
        label="Category"
      />

      {{ $data }}

      <h3>Name & describe your event</h3>

      <BaseInput v-model="event.title" type="text" label="Title" />

      <BaseInput label="Description" v-model="event.description" type="text" />

      <h3>Where is your event?</h3>

      <BaseInput v-model="event.location" label="Location" type="text" />

      <h3>Are pets allowed?</h3>

      <div>
        <BaseRadioGroup
          v-model="event.pets"
          label="Pets"
          :options="petsOptions"
        />
      </div>

      <h3>Extras</h3>
      <div>
        <BaseCheckbox label="Catering" v-model="event.extras.catering" />
      </div>

      <div>
        <BaseCheckbox label="Music" v-model="event.extras.music" />
      </div>
      <button class="button -fill-gradient" type="submit">Submit</button>
    </form>
  </div>
</template>

<script>
import BaseInput from '@/components/BaseInput.vue'
import BaseSelect from '../components/BaseSelect.vue'
import BaseCheckbox from '@/components/BaseCheckbox.vue'
import BaseRadioGroup from '@/components/BaseRadioGroup.vue'
import axios from 'axios'
export default {
  components: { BaseInput, BaseSelect, BaseCheckbox, BaseRadioGroup },
  // eslint-disable-next-line space-before-function-paren
  data() {
    return {
      categories: [
        'sustainability',
        'nature',
        'animal welfare',
        'housing',
        'education',
        'food',
        'community'
      ],
      event: {
        category: '',
        title: '',
        description: '',
        location: '',
        pets: 1,
        extras: {
          catering: false,
          music: false
        }
      },
      petsOptions: [
        {
          label: 'Yes',
          value: 1
        },
        {
          label: 'No',
          value: 0
        }
      ]
    }
  },
  methods: {
    // eslint-disable-next-line space-before-function-paren
    sendForm() {
      axios
        .post(
          'https://my-json-server.typicode.com/Code-Pop/Vue-3-Forms/events',
          this.event
        )
        .then((response) => {
          console.log(response)
        })
        .catch((error) => {
          console.log(error)
        })
    }
  }
}
</script>
