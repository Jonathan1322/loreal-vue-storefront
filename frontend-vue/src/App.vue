<script setup>
import { ref, computed, onMounted } from 'vue';


const API_BASE = 'http://localhost:3000';
const API_PATH = '/api/productos';


const productos = ref([]);
const error = ref(null);

const primerProducto = computed(() => productos.value[0] ?? null);

function urlFoto(p) {
  if (!p?.foto) return '';
  if (/^https?:\/\//i.test(p.foto)) return p.foto;       /* API pública*/
  return `${API_BASE}/imagenes/productos/${p.foto}`;      /* API local*/
}

onMounted(async () => {
  try {
    const res = await fetch(`${API_BASE}${API_PATH}`);
    if (!res.ok) throw new Error(`HTTP ${res.status}`);
    productos.value = await res.json();
  } catch (err) {
    error.value = `No se pudo cargar la información (${err.message})`;
    productos.value = [];
  }
});
</script>

<template>
  <main>
    <h1>Aplicación ejemplo FRONT-END Vue</h1>

    <p v-if="error" style="color: red; font-weight: bold;"> {{ error }}</p>

    <ul v-else>
      <li v-for="p in productos" :key="p.nombre">
        {{ p.nombre }} - {{ p.foto }} - {{ p.votacion }}
      </li>
    </ul>

    <hr />

    <section v-if="primerProducto">
      <p>
        <strong>Nombre:</strong> {{ primerProducto.nombre }}<br />
        <strong>Foto (campo):</strong> {{ primerProducto.foto }}<br />
        <strong>Votación:</strong> {{ primerProducto.votacion }}
      </p>
      <img
        :src="urlFoto(primerProducto)"
        :alt="primerProducto.nombre"
        style="max-width: 200px; border-radius: 8px;"
      />
    </section>
  </main>
</template>