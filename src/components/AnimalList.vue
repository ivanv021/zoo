<template>
    <div>
    <h1>{{ msg2 }}</h1>


        <h2>Zivotinje:</h2>
        <!-- <ul>
            
      <li v-for="(animal, index) in animals" :key="index"><br>Vrsta: {{ animal.vrsta }} <br> Ime: {{ animal.ime }} <br> Datum Rodjenja: {{ animal.datumRodjenja }} </li>
      </ul> -->


       <table  style="width:100%">
  <tr>
    <th>Vrsta</th>
    <th>Ime</th>
    <th>Datum Rodjenja</th>
    <th>Obrisi Zivotinju</th>
  </tr>
  <tr v-for="(animal, index) in animals" :key="index">
    
    <td>{{ animal.vrsta }}</td>
    <td>{{ animal.ime }}</td>
    <td ><div>{{ animal.datumRodjenja === '' ? 'Nepoznat' :  animal.datumRodjenja  }}</div> </td>
    <td><button @click="deleteAnimal(index)">Remove</button></td>
    
    
  </tr>
 
</table> 




    
   
    </div>
  
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },

  data() {
    return {

      msg2: 'Zoo',
      animals: [{ vrsta: 'Lav', ime: 'Rex', datumRodjenja: '20.11.2004.'  },
                  { vrsta: 'Slon', ime: 'Mica', datumRodjenja: '2.12.2009.'  },
                  { vrsta: 'Papagaj', ime: 'Kica', datumRodjenja: '23.5.2016.'   },
                  { vrsta: 'Kamila', ime: 'Mo', datumRodjenja: '2.4.2019.'  },
                  { vrsta: 'Majmun', ime: 'Dzon', datumRodjenja: ''   }



      ]
      
 
    };

    


  },

  methods: {

      deleteAnimal: function(index) {
      this.animals.splice(index, 1);
}

    
    }



  
  }
  




</script>


<style scoped>

table, th, td {
  border: 1px solid black;
}

</style>
