<template> 
    <div>
        <canvas id="myChart"></canvas>
    </div>
</template>

<script setup>
import Chart  from 'chart.js/auto';

const labels = [
    'January',
    'February',
    'March',
    'April',
    'May',
  ];

  const data = {
    labels: labels,
    datasets: [{
      label: 'Pengunjung',
      backgroundColor: [
        'rgb(135, 198, 119)',
        'rgb(208, 181, 84)',
        'rgb(183, 31, 31)',
        'rgb(135, 198, 119)',
        'rgb(228, 202, 107)',
      ],
      borderColor: 'rgb(255, 100, 132)',
      data: [6, 8, 10, 9, 9,],
    }]
  };

  const config = {
    type: 'bar',
    data: data,
    options: {}
  };

  onMounted(()=>{
    const myChart = new Chart(
    document.getElementById('myChart'),
    config
  );
  })
</script>