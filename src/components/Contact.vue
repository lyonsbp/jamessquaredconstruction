<template>
  <v-card>
    <v-card-title
      primary-title
      class="title accent secondary--text">
      Get a Quote
    </v-card-title>
    <v-layout justify-center>
      <v-flex xs10 lg6>
        <v-form>
          <v-text-field
            v-model="firstName"
            :error-messages="firstNameErrors"
            required
            label="First Name"
            @input="$v.firstName.$touch()"
            @blur="$v.firstName.$touch()"
          >
          </v-text-field>
          <v-text-field
            v-model="lastName"
            :error-messages="lastNameErrors"
            required
            label="Last Name"
            @input="$v.lastName.$touch()"
            @blur="$v.lastName.$touch()"
          >
          </v-text-field>
          <v-text-field
            v-model="email"
            required
            :error-messages="emailErrors"
            label="Email"
            @input="$v.email.$touch()"
            @blur="$v.email.$touch()"
          >
          </v-text-field>
          <v-text-field
            v-model="phoneNum"
            required
            mask="(###) ### - ####"
            label="Phone #"
          >
          </v-text-field>
          <v-select
            :items="serviceList"
            required
            v-model="selectedService"
            label="Service"
          ></v-select>
        </v-form>
      </v-flex>
    </v-layout>
    <v-card-actions>
      <v-layout justify-end>
        <v-flex xs3>
          <v-btn
            color="primary"
          >Submit
          </v-btn>
        </v-flex>
      </v-layout>
    </v-card-actions>
  </v-card>
</template>

<script>
import { validationMixin } from 'vuelidate'
import { required, email, maxLength } from 'vuelidate/lib/validators'
export default {
  mixins: [validationMixin],
  validations: {
    firstName: { required },
    lastName: { required },
    email: { required, email },
    phoneNum: { required, maxLength: maxLength(10) }
  },
  data () {
    return {
      firstName: '',
      lastName: '',
      phoneNum: '',
      email: '',
      serviceList: ['Roofing', 'Siding', 'Plumbing', 'Windows'],
      selectedService: ''
    }
  },
  methods: {
    nameErrors (name) {
      const errors = []
      if (!this.$v[name].$dirty) return errors
      !this.$v[name].required && errors.push('Name is required.')
      return errors
    }
  },
  computed: {
    firstNameErrors () {
      return this.nameErrors('firstName')
    },
    lastNameErrors () {
      return this.nameErrors('lastName')
    },
    emailErrors () {
      const errors = []
      if (!this.$v.email.$dirty) return errors
      !this.$v.email.email && errors.push('Must be valid e-mail')
      !this.$v.email.required && errors.push('E-mail is required')
      return errors
    }
  }
}
</script>

<style>

</style>
