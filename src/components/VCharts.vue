<template>
    <ve-heatmap :data="chartData" :settings="chartSettings"></ve-heatmap>
</template>

<script>
    var hours = [
    "00:00",
    "01:00",
    "02:00",
    "03:00",
    "04:00",
    "05:00",
    "06:00",
    "07:00",
    "08:00",
    "09:00",
    "10:00",
    "11:00",
    "12:00",
    "13:00",
    "14:00",
    "15:00",
    "16:00",
    "17:00",
    "18:00",
    "19:00",
    "20:00",
    "21:00",
    "22:00",
    "23:00",
    ];

    var days = ["Sun", "Sat", "Fri", "Thu", "Wed", "Tue", "Mon"];

    var data = [
    [0, 0, 5],
    [0, 1, 1],
    [0, 2, 1],
    [0, 3, 1],
    [0, 4, 1],
    [0, 5, 1],
    [0, 6, 1],
    [0, 7, 1],
    [0, 8, 1],
    [0, 9, 1],
    [0, 10, 2],
    [0, 11, 2],
    [0, 12, 4],
    [0, 13, 1],
    [0, 14, 1],
    [0, 15, 3],
    [0, 16, 4],
    [0, 17, 6],
    [0, 18, 4],
    [0, 19, 4],
    [0, 20, 3],
    [0, 21, 3],
    [0, 22, 2],
    [0, 23, 5],
    [1, 0, 7],
    [1, 1, 4],
    [1, 2, 4],
    [1, 3, 4],
    [1, 4, 4],
    [1, 5, 4],
    [1, 6, 3],
    [1, 7, 3],
    [1, 8, 3],
    [1, 9, 3],
    [1, 10, 5],
    [1, 11, 2],
    [1, 12, 2],
    [1, 13, 6],
    [1, 14, 9],
    [1, 15, 11],
    [1, 16, 6],
    [1, 17, 7],
    [1, 18, 8],
    [1, 19, 12],
    [1, 20, 5],
    [1, 21, 5],
    [1, 22, 7],
    [1, 23, 2],
    [2, 0, 1],
    [2, 1, 1],
    [2, 2, 7],
    [2, 3, 7],
    [2, 4, 7],
    [2, 5, 7],
    [2, 6, 3],
    [2, 7, 3],
    [2, 8, 3],
    [2, 9, 3],
    [2, 10, 3],
    [2, 11, 2],
    [2, 12, 1],
    [2, 13, 9],
    [2, 14, 8],
    [2, 15, 10],
    [2, 16, 6],
    [2, 17, 5],
    [2, 18, 5],
    [2, 19, 5],
    [2, 20, 7],
    [2, 21, 4],
    [2, 22, 2],
    [2, 23, 4],
    [3, 0, 7],
    [3, 1, 3],
    [3, 2, 8],
    [3, 3, 8],
    [3, 4, 0],
    [3, 5, 0],
    [3, 6, 8],
    [3, 7, 8],
    [3, 8, 1],
    [3, 9, 8],
    [3, 10, 5],
    [3, 11, 4],
    [3, 12, 7],
    [3, 13, 14],
    [3, 14, 13],
    [3, 15, 12],
    [3, 16, 9],
    [3, 17, 5],
    [3, 18, 5],
    [3, 19, 10],
    [3, 20, 6],
    [3, 21, 4],
    [3, 22, 4],
    [3, 23, 1],
    [4, 0, 1],
    [4, 1, 3],
    [4, 2, 5],
    [4, 3, 5],
    [4, 4, 5],
    [4, 5, 1],
    [4, 6, 0],
    [4, 7, 0],
    [4, 8, 0],
    [4, 9, 2],
    [4, 10, 4],
    [4, 11, 4],
    [4, 12, 2],
    [4, 13, 4],
    [4, 14, 4],
    [4, 15, 14],
    [4, 16, 12],
    [4, 17, 1],
    [4, 18, 8],
    [4, 19, 5],
    [4, 20, 3],
    [4, 21, 7],
    [4, 22, 3],
    [4, 23, 1],
    [5, 0, 2],
    [5, 1, 1],
    [5, 2, 1],
    [5, 3, 3],
    [5, 4, 1],
    [5, 5, 1],
    [5, 6, 1],
    [5, 7, 1],
    [5, 8, 2],
    [5, 9, 0],
    [5, 10, 4],
    [5, 11, 1],
    [5, 12, 5],
    [5, 13, 10],
    [5, 14, 5],
    [5, 15, 7],
    [5, 16, 11],
    [5, 17, 6],
    [5, 18, 0],
    [5, 19, 5],
    [5, 20, 3],
    [5, 21, 4],
    [5, 22, 2],
    [5, 23, 0],
    [6, 0, 1],
    [6, 1, 1],
    [6, 2, 1],
    [6, 3, 1],
    [6, 4, 1],
    [6, 5, 1],
    [6, 6, 1],
    [6, 7, 1],
    [6, 8, 1],
    [6, 9, 1],
    [6, 10, 1],
    [6, 11, 0],
    [6, 12, 2],
    [6, 13, 1],
    [6, 14, 3],
    [6, 15, 4],
    [6, 16, 1],
    [6, 17, 1],
    [6, 18, 1],
    [6, 19, 1],
    [6, 20, 1],
    [6, 21, 2],
    [6, 22, 2],
    [6, 23, 6],
    ];

    export default {
    data() {
        const rows = [];
        data = data.forEach((item) => {
        rows.push({
            week: days[item[0]],
            hours: hours[item[1]],
            points: item[2],
        });
        });

        return {
        chartSettings: {
            heatColor: ["#fff", "#1500ff"],
        },
        chartData: {
            columns: ["hours", "week", "points"],
            rows: rows,
        },
        };
    },
};
</script>