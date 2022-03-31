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
        <BaseRadio v-model="event.pets" :value="1" label="Yes" name="pets" />
      </div>

      <div>
        <BaseRadio v-model="event.pets" label="No" :value="0" name="pets" />
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
import BaseRadio from '@/components/BaseRadio.vue'
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
  components: { BaseInput, BaseSelect, BaseCheckbox, BaseRadio }
}
</script>
