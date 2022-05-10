<template>
  <hr />
  <div class="titulo">
    <h1>ABP 6.2</h1>
  </div>
  <hr />
  <input type="text" v-model="filtro" placeholder="Filtrar por Nombre" />
  <hr />
  <div class="Pokemon">
    <div class="container fluid">
      <table class="table bg-info text-white">
        <thead class="bg-primary">
          <tr>
            <th scope="col">Id</th>
            <th scope="col">Nombre</th>
            <th scope="col">Descripcion</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(Personaje, index) in filtroNombres" :key="index">
            <th>{{ Personaje.id }}</th>
            <td>{{ Personaje.nombre }}</td>
            <td>{{ Personaje.descripcion }}</td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: "Personajes",
  data: () => ({
    Personajes: [
      {
        id: "1",
        nombre: "picachu",
        descripcion: "lorem ipsum uhiuhiuhihoi",
      },
      {
        id: "2",
        nombre: "kakuna",
        descripcion: "lorem ipsum uhiuhiuhihoi",
      },
      {
        id: "3",
        nombre: "beedrill",
        descripcion: "lorem ipsum uhiuhiuhihoi",
      },
      {
        id: "4",
        nombre: "metapod",
        descripcion: "lorem ipsum uhiuhiuhihoi",
      },
      {
        id: "5",
        nombre: "rattata",
        descripcion: "lorem ipsum uhiuhiuhihoi",
      },
    ],

    filtro: ''
  }),

  computed:{
    filtroNombres: function(){
      return this.Personajes.filter((Personaje) => {
        return Personaje.nombre.match(this.filtro);
      })
    }
  }
};


</script>

<style>
.pokemon {
  background-color: rgb(196, 255, 214);
}
</style>

/* https://www.youtube.com/watch?v=G34_yNV8FMY */