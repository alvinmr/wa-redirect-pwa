<template>
  <div class="flex justify-center h-screen">
    <div class="flex flex-col self-center text-center">
      <h1 class="mb-10 text-2xl font-bold tracking-widest text-center">WA DIRECT🤙</h1>
      <input
        class="p-3 overflow-hidden border-4 border-black focus:outline-none"
        type="number"
        name="nomor"
        placeholder="Cth : 628537748362"
        autocomplete="off"
        v-model="nomor"
        pattern="[0-9]*"
        inputmode="numeric"
      />
      <a
        v-if="loading"
        class="px-2 py-4 mt-4 font-bold text-white bg-red-600"
        @click="chat"
      >Mulai Chat</a>
      <a class="px-2 py-4 mt-4 font-bold text-white bg-red-600" v-else>Loading</a>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      nomor: "",
      loading: true,
    };
  },
  methods: {
    chat(e) {
      if (this.nomor) {
        this.loading = false;
        window.location.href = `https://api.whatsapp.com/send?phone=${this.nomor}`;
        this.loading = true;
      } else {
        e.preventDefault;
      }
    },
  },
};
</script>

<style>
* {
  font-family: "DM Mono", monospace;
}
</style>
