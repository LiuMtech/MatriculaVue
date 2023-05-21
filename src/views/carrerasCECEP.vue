<template>
    <div class="container" id="carreras">
        <h1>Carreras List</h1>
        <table class="table">
  <thead>
    <tr>
      <th scope="col">#</th>
      <th scope="col">Carreras</th>
    </tr>
  </thead>
  <tbody>
    <tr tr v-for="(carreras,index) in carreras " :key="index">
      <th scope="row">{{ index + 1 }}</th>
      <td>{{carreras.nom_Carrera}}</td>
    </tr>
  </tbody>
</table>
    </div>
    </template>
    
    <script>
    import axios from 'axios'
    export default{
    
        name: 'carreras',
        data(){
            return{
                carreras: []
            }
        },
        mounted() {
            axios.get('http://127.0.0.1:8000/api/carreras').then(response => {this.carreras = response.data.carreras;
            });
        },
    
    }
    
    </script>