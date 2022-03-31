<template>
  <div>
    <h1>Create an event</h1>
    <form>
      <BaseSelect
        :options="categories"
        v-model="event.category"
        label="Category"
      />

      {{ $data }}

      <h3>Name & describe your event</h3>

      <BaseInput label="Title" v-model="event.title" type="text" />

      <BaseInput label="Description" v-model="event.description" type="text" />

      <h3>Where is your event?</h3>

      <BaseInput v-model="event.location" label="Location" type="text" />

      <h3>Are pets allowed?</h3>
      <div>
        <input type="radio" v-model="event.pets" :value="1" name="pets" />
        <label>Yes</label>
      </div>

      <div>
        <input type="radio" v-model="event.pets" :value="0" name="pets" />
        <label>No</label>
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
export default {
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
      }
    }
  },
  components: { BaseInput, BaseSelect, BaseCheckbox }
}
</script>
