<template>
<div>
<div class = 'title'>
    <h1> Placar </h1>
</div>
    <table>
        <thead>
            <tr>
                <td>Colocação: </td>
                <td>Pontuação: </td>
                <td>Data: </td>
            </tr>
        </thead>
        <tbody>
            <tr v-for="(data, index) in $options.leaderboard">
                <td>Top {{index+1}}</td>
                <td> {{parseFloat(data.score).toFixed(2)}}</td>
                <td>{{toDateTime(data.time)}}</td>
            </tr>
        </tbody>
    </table>
    <ul>
        <li class='dark'><NuxtLink to="/"> Voltar </NuxtLink> </li>
    </ul>
</div>
</template>


<style>
.dark{
    color:#272727;
}
    .title{
        text-align: center;
    }
  table {
        width: 100%;
        border: 1px solid #ddd;
        }

        td {
        padding: 16px;
        }

        tr:nth-child(even) {
        background-color: #eee;
        }
</style>
<script>
      import json from '~/assets/Leaderboard.json'
      export default{
          methods: {
              toDateTime: (secs) => {
                var d = new Date(1970, 0, 1);
                d.setSeconds(secs/1000);
                var datestring = d.getDate()  + "-" + (d.getMonth()+1) + "-" + d.getFullYear() + " " +
d.getHours() + ":" + d.getMinutes();
                return datestring;
          }
          },
        leaderboard: json,
        }
      

    
    
</script>