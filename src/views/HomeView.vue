<script setup>
import { useProductStore } from '@/stores/product';
import { useRouter } from 'vue-router';
const productStore = useProductStore();
const router = useRouter();

function view(id) {
  router.push(`/product/${id}`); //template strings
}
</script>

<template>
<h1>Listagem de Produtos</h1>
<table>
  <thead>
    <tr>
      <th>#</th>
      <th>Nome</th>
      <th>Preço</th>
      <th>Ações</th>
    </tr>
  </thead>
  <tbody>
    <tr v-for="product in productStore.products" :key="product.id">
    <td>{{ product.id }}</td>
    <td>{{ product.name }}</td>
    <td>{{ product.price }}</td>
    <td>
      <button @click="view(product.id)">Ver</button>
    </td>
    </tr>

  </tbody>
</table>

</template>
