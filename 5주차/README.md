
# 영화 랜덤 돌리기 기능 구현

```bash

<body>


    <img src="https://search.pstatic.net/common?quality=75&direct=true&src=https%3A%2F%2Fmovie-phinf.pstatic.net%2F20180406_37%2F1522991036857QqP7N_JPEG%2Fmovie_image.jpg"
         id="movie" width="300px" height="200px">

    <button onclick="change()">행운의 럭키</button>

    <script>
        var image = [
            "https://search.pstatic.net/common?quality=75&direct=true&src=https%3A%2F%2Fmovie-phinf.pstatic.net%2F20120718_209%2F1342589585791cltsr_JPEG%2Fmovie_image.jpg",
            "https://search.pstatic.net/common?quality=75&direct=true&src=https%3A%2F%2Fmovie-phinf.pstatic.net%2F20240425_256%2F17140073560223JK9r_JPEG%2Fmovie_image.jpg",
            "https://search.pstatic.net/common?quality=75&direct=true&src=https%3A%2F%2Fmovie-phinf.pstatic.net%2F20180406_37%2F1522991036857QqP7N_JPEG%2Fmovie_image.jpg"
        ];

        function change() {
            var randomIndex = Math.floor(Math.random() * image.length);
            var movie = document.getElementById("movie");
            movie.src = image[randomIndex];
        }
    </script>
</body>
```

