<template>
  <q-page class="q-pa-md">
    <q-form @submit="onSubmit" @reset="onReset" class="q-gutter-md">
      <q-input
        v-model="name"
        label="Your name *"
        hint="Name and surname"
        lazy-rules
        :rules="[val => !!val || 'Please enter your name']"
      />

      <q-input
        v-model.number="age"
        label="Your age *"
        type="number"
        lazy-rules
        :rules="[val => !!val || 'Please enter your age']"
      />

      <q-checkbox
        v-model="accept"
        label="I accept the license and terms"
      />

      <div>
        <q-btn label="SUBMIT" type="submit" color="primary" />
        <q-btn
          label="RESET"
          type="reset"
          color="primary"
          flat
          class="q-ml-sm"
        />
      </div>
    </q-form>
  </q-page>
</template>

<script setup>
import { ref } from 'vue'

const name = ref(null)
const age = ref(null)
const accept = ref(false)

function onSubmit () {
  console.log('Submitted', {
    name: name.value,
    age: age.value,
    accept: accept.value
  })
}

function onReset () {
  name.value = null
  age.value = null
  accept.value = false
}
</script>
