<template>
    <q-page>
    Halaman Register
    <q-form
      @submit="onSubmit"
      @reset="onReset"
      class="q-gutter-md">
      <q-input
        filled
        v-model="Name"
        label="Nama Lengkap *"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Tolong Ketik Nama Lengkap Anda']"
      />
      <q-input
        filled
        v-model="Username"
        label="Username *"
        lazy-rules
        :rules="[val => val !== null && val.length > 0 || 'Tolong Ketik Username Anda']"
      />
      <q-input
        filled
        type="password"
        v-model="Password"
        label="Your password *"
        lazy-rules
        :rules="[
          val => val !== null && val.length > 0 || 'Tolong Ketik Password Anda'
        ]"
      />
      <q-input
        filled
        v-model="Email"
        label="Alamat Email *"
        lazy-rules
        :rules="[val => val !== null && val.length > 0 || 'Tolong Ketik Alamat Email Anda']"
      />
      <div>
        <q-btn label="Daftar" type="daftar" color="primary"/>
        <q-btn label="Kembali" type="kembali" color="primary" flat class="q-ml-sm" />
      </div>
    </q-form>
    </q-page>
</template>
<script>
export default {
  data () {
    return {
      Name: null,
      Username: null,
      Password: null,
      Email: null
    }
  },
  methods: {
    onSubmit () {
      console.log('Ini fungsi daftar')
    },
    onReset () {
      console.log('ini fungsi kembali')
    }
  }
}
</script>
