# 4주차 | HTML 뼈대 구축

## 첫번째 홈 페이지
- 검정색 바탕화면과 빨간색으로 모든 전체적인 화면 컨셉 구성

![image](https://github.com/user-attachments/assets/24fb33e8-287d-4926-a1dc-04fb16b23231)

- 영화 추천 보기 버튼 클릭 시 다음 페이지로 이동

## 두번째 페이지

- 화면 메인에 '오늘의 PICK'와 '평론가의 PICK'으로 나누어 영화 포스터와 함께 중앙에 배치
- '장르별', '랜덤영화', '내가 찜한 리스트', '평론가의 PICK'으로 4개의 버튼 배치 -> 클릭시 각 페이지로 이동
  
![image](https://github.com/user-attachments/assets/4cdd883f-c22f-423f-a988-e030338c6858)

```bash
 <div class="genre-filter">

<a href="장르별.html"#movies" class="btn">장르별</a>
<a href="랜덤 영화.html"#movies" class="btn">랜덤 영화</a>
<a href="내가 찜한 리스트.html"#movies" class="btn">내가 찜한 리스트</a>
<a href="평론가 픽.html"#movies" class="btn">평론가 Pick</a>
 </div>


<div style="display: flex; flex-direction: row; align-items: center; justify-content: center;">
  <h2>오늘의 Pick</h2>
  <h2 style="margin-left: 250px;">평론가의 Pick</h2>
</div>
<div style="text-align: center;">
 <a href="https://www.youtube.com/watch?v=MFXWhpcuIg4" class="poster-link" target="_blank" rel="noopener noreferrer"><img src="https://search.pstatic.net/common?quality=75&direct=true&src=https%3A%2F%2Fmovie-phinf.pstatic.net%2F20250207_265%2F1738893336962Cn1Vd_JPEG%2Fmovie_image.jpg"  width="450" height="700">

<a href="https://www.youtube.com/watch?v=qLMmHsSSBhc" class="poster-link" target="_blank" rel="noopener noreferrer"><img src="https://search.pstatic.net/common?quality=75&direct=true&src=https%3A%2F%2Fmovie-phinf.pstatic.net%2F20250224_285%2F17403736827925oq24_JPEG%2Fmovie_image.jpg"  width="450" height="700"   style="cursor: pointer;"
    alt="미키17 포스터">

</div>
```
## 장르별.html
- '전체', '액션', '코미디', ' SF', '공포', '로맨스'로 총 5개의 장르로 나누어 그에 맞는 영화 포스터 소개.
- '전체' 버튼 클릭 시 5개의 장르 영화가 합해진 모든 영화 포스터 나열
  
![image](https://github.com/user-attachments/assets/5c7f008c-f59a-467f-a730-46fb30b10328)


- '도둑들' 카드 뉴스 예시
  
 ```bash
   .movie-card {
      background-color: black;
      border-radius: 12px;
      box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
      overflow: hidden;
      transition: transform 0.2s;
    }

    .movie-card:hover {
      transform: translateY(-5px);
    }

    .movie-card img {
      width: 100%;
      height: 300px;
      object-fit: cover;
    }

    .movie-card .info {
      padding: 15px;
    }
```

```bash
 <div class="movie-container">
    <div class="movie-card">
    <div style="display: flex; flex-direction: row; gap: 15px; flex-wrap: wrap;">
        
      <img src="https://search.pstatic.net/common?quality=75&direct=true&src=https%3A%2F%2Fmovie-phinf.pstatic.net%2F20120718_209%2F1342589585791cltsr_JPEG%2Fmovie_image.jpg" alt="영화 포스터" 
        width="200" height="300">
   
      <div class="movie-info">
        <h3><a href="도둑들.html" style=" margin: 0; font-size: 18px; color: inherit;">도둑들</h3></a>
        <p>10인의 도둑 1개의 다이아몬드 그들이 움직이기 시작했다.</p>
    </div>
     </div>
    </div>
  ```

## 랜덤영화.html

- 버튼 클릭 시 랜 기능 실현

![image](https://github.com/user-attachments/assets/3ce8e56d-6eac-4471-b578-3020e3ad3925)


## 내가 찜한 영화.html

- 모든 영화 카드 뉴스로 나열
- '상세 보기'와 '찜 취소' 두개의 버튼으로 구성

![image](https://github.com/user-attachments/assets/5f46bbf4-07fb-431b-857d-faa01921a968)

```bash
<div class="container">
        <h2 class="wishlist-title">내가 찜한 영화</h2>
        
        <div id="wishlistContainer" class="wishlist-container">
            <!-- 찜 목록이 여기에 동적으로 추가됩니다 -->
        </div>
        
        <div id="emptyWishlist" class="empty-wishlist" style="display: none;">
            <p>찜한 영화가 없습니다.</p>
            <p>마음에 드는 영화를 찜해보세요!</p>
            <a href="액션.html" class="back-link">영화 목록으로 돌아가기</a>
        </div>
    </div>

    <script>
        document.addEventListener('DOMContentLoaded', function() {
            const wishlistContainer = document.getElementById('wishlistContainer');
            const emptyWishlist = document.getElementById('emptyWishlist');
            
            // 로컬 스토리지에서 찜 목록 불러오기
            const wishlist = JSON.parse(localStorage.getItem('movieWishlist')) || {};
            
            // 찜 목록이 비어있는지 확인
            if (Object.keys(wishlist).length === 0) {
                emptyWishlist.style.display = 'block';
                return;
            }
            
            // 찜 목록 표시
            for (const movieId in wishlist) {
                const movie = wishlist[movieId];
                
                // 영화 카드 요소 생성
                const movieCard = document.createElement('div');
                movieCard.className = 'movie-card';
                movieCard.dataset.id = movieId;
                
                // 영화 카드 내용 생성
                movieCard.innerHTML = `
                    <div class="movie-poster">
                        <img src="${movie.poster}" alt="${movie.title} 포스터">
                    </div>
                    <div class="movie-title">${movie.title}</div>
                    <div class="movie-actions">
                        <a href="${movie.url}" class="btn">상세보기</a>
                        <button class="btn remove-btn" data-id="${movieId}">찜 취소</button>
                    </div>
                `;
                
                // 영화 카드를 컨테이너에 추가
                wishlistContainer.appendChild(movieCard);
            }
            
            // 찜 취소 버튼 이벤트 설정
            document.querySelectorAll('.remove-btn').forEach(button => {
                button.addEventListener('click', function() {
                    const movieId = this.dataset.id;
                    
                    // 로컬 스토리지에서 찜 목록 불러오기
                    const wishlist = JSON.parse(localStorage.getItem('movieWishlist')) || {};
                    
                    // 찜 목록에서 제거
                    if (wishlist[movieId]) {
                        delete wishlist[movieId];
                        localStorage.setItem('movieWishlist', JSON.stringify(wishlist));
                        
                        // DOM에서 영화 카드 제거
                        document.querySelector(`.movie-card[data-id="${movieId}"]`).remove();
                        
                        // 찜 목록이 비어있는지 확인
                        if (Object.keys(wishlist).length === 0) {
                            emptyWishlist.style.display = 'block';
                        }
                        
                        alert('찜 목록에서 제거되었습니다.');
                    }
                });
            });
        });
    </script>
```

## 평론가 PICK.html

![image](https://github.com/user-attachments/assets/bef1dd82-5242-43e4-ae18-edc07231543c)

```bash
<table>
  <thead>
    <tr>
      <th>포스터</th>
      <th>제목</th>
      <th>감독</th>
      <th>장르</th>
      <th>찜</th>
      <th>한줄평</th>
    </tr>
  </thead>
  <tbody>
    <tr data-id="1" data-comment="빛은 어디에서 오는가, 과거는 어디에 맺히는가.">
      <td><img src="https://i.namu.wiki/i/azaANEcoUB3Yes5FpcxwFImnBglqNGHugGA-a4iGLuM5A5zpAkGxoxm8mCBSB3VmFf7MZUGpUIi2k0HCjTXrJLV68Ezj_8ef-ADIxMUmfvf_EzWAv8LifhrXLp2dxGif6m5bg-2TjA6qwsJV6r073w.webp" alt="브루탈리스트"></td>
      <td>브루탈리스트(2025)</td>
      <td>브래디 코베</td>
      <td>드라마</td>
      <td><button class="btn wishlist-btn">찜하기 ♥</button></td>
      <td><button class="btn comment-btn">보기</button></td>
    </tr>
```
