<template>
  <div>
    <div v-for="user in users" :key="user">
      <p>{{ user.name }}</p>
      <p>{{ user.cpf }}</p>
      <button @click="copy(user.cpf)">Copiar Num</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cpf: "",
      users: [
        {
          name: "Jairo",
          cpf: "102.102.102-32",
        },
        {
          name: "Julio",
          cpf: "321.321./321-36",
        },
      ],
    };
  },
  methods: {
    copy(cpfcnpj) {
      cpfcnpj = cpfcnpj.replace(/[./-]/g, "");
      console.log(cpfcnpj);
      navigator.clipboard.writeText(cpfcnpj);
    },
  },
};
</script>

<style></style>
