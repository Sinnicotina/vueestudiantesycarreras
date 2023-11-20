<template>
    <div class="container">
        <h1>listado Carreras</h1>
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
                <tr v-for="(carrera,index) in carreras" :key="index">
                    <th scope="row">{{index+1}}</th>
                    <td>{{carrera.carre_codi}}</td>
                    <td>{{carrera.carre_nomb}}</td>
                    <td>{{carrera.espe_nomb}}</td>
                </tr>
            </tbody>

        </table>
        
    </div>
</template>
<script>
import axios from 'axios';
export default{
    name:'Carrera',
    data() {
        return {
            carreras:[]
        }
    },
    mounted() {
        axios
        .get('http://127.0.0.1:8000/api/carreras')
        .then(response=>(this.carreras=response.data.carreras))
    },
}
</script>