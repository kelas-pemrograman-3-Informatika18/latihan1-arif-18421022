<template>
    <q-page class="bg-white-3">
      <div class="row">
      <q-card class="fixed-center col-md-4 col-xs-12 bg-white" flat>
      <q-card-section>
      <div class="text-h6 q-pb-md">
    Halaman login
      </div>
      <q-form
      @submit="onSubmit"
      @reset="onReset"
      class="q-gutter-md"
    >
      <q-input
        filled
        v-model="username"
        label="Username *"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Tolong Ketik Username Anda']"
      />

      <q-input
        filled
        type="password"
        v-model="password"
        label="Password *"
        lazy-rules
        :rules="[
          val => val !== null && val.length > 0 || 'Tolong Ketik Password Anda'
        ]"
      />
      <div>
        <q-btn label="Login" type="submit" color="primary"/>
        <q-btn label="Register" type="reset" color="primary" flat class="q-ml-sm" />
      </div>
      </q-form>
      </q-card-section>
      </q-card>
      </div>
      </q-page>
</template>
<script>
export default {
  data () {
    return {
      username: null,
      password: null
    }
  },
  methods: {
    onSubmit () {
      if (this.username === 'arif' && this.password === '123') {
        this.$q.notify({
          type: 'positive',
          message: 'Selamat Berhasil Login'
        })
        this.$router.push('/home')
      } else {
        this.$q.notify({
          type: 'negative',
          message: 'Gagal Login, Username/Password Salah'
        })
      }
    },
    onReset () {
      this.username = null
      this.password = null
    }
  }
}
</script>
