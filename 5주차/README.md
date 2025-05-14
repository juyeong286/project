# 5주차 | 기능 구체화

## - 포스터 클릭 시 영화 예고편 재생 기능

![image](https://github.com/user-attachments/assets/d9de0524-c68f-415d-a9ec-47cb7c768129)

![image](https://github.com/user-attachments/assets/05e6e0e7-51a7-4b6d-97a2-ed3d2c6f7ac9)

```bash
div style="text-align: center;">
 <a href="https://www.youtube.com/watch?v=MFXWhpcuIg4" class="poster-link" target="_blank" rel="noopener noreferrer"><img src="https://search.pstatic.net/common?quality=75&direct=true&src=https%3A%2F%2Fmovie-phinf.pstatic.net%2F20250207_265%2F1738893336962Cn1Vd_JPEG%2Fmovie_image.jpg"  width="450" height="700">
```

## - 영화 포스터 클릭 시 영화 상세 설명 이동

![image](https://github.com/user-attachments/assets/b84ef6b3-6875-4c7d-ae31-7c7a345c2ace)

![image](https://github.com/user-attachments/assets/333e65d6-1df7-42fa-adbc-a2bb2aa2764f)

-> 영화 포스터 클릭 시 영화 예고편으로 이동

```bash

<div class="info-container">
   
 <h1 class="movie-title">도둑들(2012)</h1>


 <div class="box1">
     <div class="rating">
    <h2><div class="detail-row"><감독> 최동훈</div>
     
       <div class="detail-row"><개봉>  2012.07.25</div>
          <div class="detail-row"><주연> 김윤석, 김혜수, 이정재, 전지현, 김해숙, 오달수</div>
          <div class="detail-row"><줄거리>  </div>
            <div class="detail-row">한 팀으로 활동 중인 한국의 도둑 뽀빠이와 예니콜, 씹던껌, 잠파노. 미술관을 터는데 멋지게 성공한 이들은 뽀빠이의 과거 파트너였던 마카오박이 제안한 홍콩에서의 새로운 계획을 듣게 된다. 여기에 마카오박이 초대하지 않은 손님, 감옥에서 막 출소한 금고털이 팹시가 합류하고 5명은 각자 인생 최고의 반전을 꿈꾸며 홍콩으로 향한다. 홍콩에서 한국 도둑들을 기다리고 있는 4인조 중국도둑 첸, 앤드류, 쥴리, 조니. 최고의 전문가들이 세팅된 가운데 서로에 대한 경계를 늦추지 않는 한국과 중국의 도둑들. 팽팽히 흐르는 긴장감 속에 나타난 마카오박은 자신이 계획한 목표물을 밝힌다. 그것은 마카오 카지노에 숨겨진 희대의 다이아몬드 <태양의 눈물>. 성공을 장담할 수 없는 위험천만한 계획이지만 2천만 달러의 달콤한 제안을 거부할 수 없는 이들은 태양의 눈물을 훔치기 위한 작업에 착수한다. 그러나 진짜 의도를 알 수 없는 비밀스런 마카오박과 그런 마카오박의 뒤통수를 노리는 뽀빠이, 마카오박에게 배신당한 과거의 기억을 잊지 못하는 팹시와 팀보다 눈 앞의 현찰을 먼저 챙기는 예니콜, 그리고 한국 도둑들을 믿지 않는 첸과 중국 도둑들까지. 훔치기 위해 모였지만 목적은 서로 다른 10인의 도둑들은 서서히 자신만의 플랜을 세우기 시작하는데…</div>
             <div class="detail-row"> </div>
          <div class="detail-row"><평점>  
                     <span class="star">★</span>
                     <span class="star">★</span>
                     <span class="star">★</span>
                     <span class="star">★</span>
                     <span class="star">★</span>
                     <span class="rating-value" id="ratingValue">5/5</span></div>
     </div>
```

## - 버튼 클릭 시 랜덤으로 영화 변환

![image](https://github.com/user-attachments/assets/4863c83d-990b-459e-be8d-8d1744487def)

![image](https://github.com/user-attachments/assets/2092b133-cf9d-4f23-b240-10d5159050c4)

[랜덤영화 예시]

```bash
<body>
 
    <img src="https://search.pstatic.net/common?quality=75&direct=true&src=https%3A%2F%2Fmovie-phinf.pstatic.net%2F20180406_37%2F1522991036857QqP7N_JPEG%2Fmovie_image.jpg"
         id="movie" width="450px" height="700px">
         <div class="genre-filter">

    <button class="genre-btn" onclick="change()">행운의 MOVIE</button>
    <script>
      
  var image = [
            "https://search.pstatic.net/common?quality=75&direct=true&src=https%3A%2F%2Fmovie-phinf.pstatic.net%2F20120718_209%2F1342589585791cltsr_JPEG%2Fmovie_image.jpg" ,
            "https://search.pstatic.net/common?quality=75&direct=true&src=https%3A%2F%2Fmovie-phinf.pstatic.net%2F20240425_256%2F17140073560223JK9r_JPEG%2Fmovie_image.jpg",
            " https://search.pstatic.net/common?quality=75&direct=true&src=https%3A%2F%2Fmovie-phinf.pstatic.net%2F20181207_251%2F1544171902408ajzP0_JPEG%2Fmovie_image.jpg"
```

## - 찜 기능 구현

![image](https://github.com/user-attachments/assets/5c5e068f-160f-4790-9bc9-d6bd10724978)

-> 영화 포스터 클릭 시 

![image](https://github.com/user-attachments/assets/98629d38-a826-45f4-b691-4e5af315b7ef)

-> '찜하기' 버튼 클릭

![image](https://github.com/user-attachments/assets/005823e1-66f5-4a65-9c6a-004a8ce752ff)

-> "찜 목록이 추가되었습니다." 화면

![image](https://github.com/user-attachments/assets/eccf4d44-6240-4792-8bf3-a8d45811f622)

-> '찜 취소' 버튼 클릭 시 -> "찜 목록에서 제거되었습니다." 화면

```bash
 <script>
    document.addEventListener('DOMContentLoaded', function() {
        const movieId = 'do2010';  // 유니크한 ID
        const movieTitle = '도둑들';
        const moviePoster = 'https://search.pstatic.net/common?quality=75&direct=true&src=https%3A%2F%2Fmovie-phinf.pstatic.net%2F20120718_209%2F1342589585791cltsr_JPEG%2Fmovie_image.jpg';
        const wishlistBtn = document.getElementById('wishlistBtn');

        const wishlist = JSON.parse(localStorage.getItem('movieWishlist')) || {};

        // 초기 버튼 상태 설정
        if (wishlist[movieId]) {
            wishlistBtn.classList.add('active');
            wishlistBtn.textContent = '찜 취소 ♥';
        }

        // 버튼 클릭 이벤트
        wishlistBtn.addEventListener('click', function () {
            if (wishlist[movieId]) {
                // 찜 취소
                delete wishlist[movieId];
                wishlistBtn.classList.remove('active');
                wishlistBtn.textContent = '찜하기 ♥';
                alert('찜 목록에서 제거되었습니다.');
            } else {
                // 찜 추가
                wishlist[movieId] = {
                    id: movieId,
                    title: movieTitle,
                    poster: moviePoster,
                    url: window.location.href
                };
                wishlistBtn.classList.add('active');
                wishlistBtn.textContent = '찜 취소 ♥';
                alert('찜 목록에 추가되었습니다.');
            }

            localStorage.setItem('movieWishlist', JSON.stringify(wishlist));
        });
    });
</script>
```


