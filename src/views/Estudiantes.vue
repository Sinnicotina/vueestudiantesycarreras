<template>
    <div class="container">
        <h1>listado Estudiantes</h1>
        <table class="table">
            <thead>
                <tr>
                    <th scope="col">#</th>
                    <th scope="col">code</th>
                    <th scope="col">Name</th>
                    <th scope="col">Carrera</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="(estudiante,index) in estudiantes" :key="index">
                    <th scope="row">{{index+1}}</th>
                    <td>{{estudiante.estu_codi}}</td>
                    <td>{{estudiante.estu_nom}}</td>
                    <td>{{estudiante.carre_nomb}}</td>
                </tr>
            </tbody>

        </table>
        
    </div>
</template>
<script>
import axios from 'axios';
export default{
    name:'Estudiante',
    data() {
        return {
            estudiantes:[]
        }
    },
    mounted() {
        axios
        .get('http://127.0.0.1:8000/api/estudiantes')
        .then(response=>(this.estudiantes=response.data.estudiantes))
    },
}
</script>