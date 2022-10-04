<template>
    <form @submit.prevent="registrarProyecto">
    <div class="mb-3">
      <label class="form-label">Proyecto</label>
      <input v-model.trim="proyecto" type="text" class="form-control" required />
    </div>
    <div class="mb-3">
      <label class="form-label">Actividad</label>
      <select v-model="tipo" class="form-selected" required>
        <option disabled selected value="">Selecciona un tipo de actividad</option>
        <option >Aplicaciones WEb con Vue.js</option>
        <option >Backend Services con Node.js</option>
        <option >App móvil con React Native</option>
      </select>
    </div>
    <div class="mb-3">
      <label class="form-check-label" >Urgentee. .</label>
      <input v-model="urgente" class="form-check-input" type="checkbox"/>
    </div>
    <button type="submit" class="btn btn-primary">Guardar</button>
</form>
<hr>
<div class="table responsive">
  <table class="table table-dark">
    <thead>
      <tr>
        <th>#</th>
        <th>Proyecto</th>
        <th>Tipo</th>
        <th>Urgente</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>1</td>
        <td>Laravel app</td>
        <td>Laravel</td>
        <td class="bg-success">Si/No</td>
      </tr>
    </tbody>
  </table>
</div>
</template>

<script>
    export default {
      data: () => ({
        proyecto: "",
        tipo:"",
        urgente: false,
        proyectos: [],
      }),
      methods: {
        registrarProyecto() {
          const proyectos = {
            proyecto: this.proyecto,
            tipo: this.tipo,
            urgente: this.urgente,
          };
          this.proyectos.push(proyectos);
          
          this.proyecto = "";
          this.tipo = "";
          this.urgente = "";
        },
      },
    };
  </script>