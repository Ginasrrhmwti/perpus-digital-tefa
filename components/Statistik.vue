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
      backgroundColor: 'rgb(255, 99, 132)',
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