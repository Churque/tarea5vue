<template>
  <div class="card" style="width: 18rem">
    <img
      class="card-img-top"
      :src="`${user.picture.medium}`"
      alt="Card image cap"
    />
    <div class="card-body">
      <h5 class="card-title">
       <p><strong>Nombre:</strong> {{ user.name.title }} {{ user.name.first }} {{ user.name.last }}</p>
      </h5>
      <div class="container-md">
        <h5 class="card-text">
          <p><strong>Genero:</strong> {{ user.gender }}</p>
          <p><strong>Pais:</strong> {{ user.location.country }}</p>
        </h5>
        <div v-if= "user.dob.age >= 18" class="alert alert-primary" role="alert">MAYOR</div>
        <div v-else class="alert alert-danger" role="alert"> MENOR </div>
      </div>
      <h5 class="card-text"></h5>
      <button
        type="button"
        class="btn"
        :class="user.gender === 'male' ? 'btn-primary' : 'btn-purple'"
        @click="mostrarMásInformacion()"
      >
        más informacion
      </button>
       <div v-if="estado" class="container-fluid mt-3 p-0">
          <p><strong>Correo: </strong>{{user.email}}</p>
          <p><strong>Ciudad: </strong>{{user.location.city}}</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "UsersCard",
  props: {
    user: {
      type: Array,
      default: () => [],
    },
  },
  methods:{
    mostrarMásInformacion() {
      this.estado = !this.estado;
    }
  },

  data(){
    return{
      estado: false,
    };
  },
};
</script>

<style>
.btn-purple {
  color: white;
  background-color: purple;
  border-color: purple ;
}

</style>
