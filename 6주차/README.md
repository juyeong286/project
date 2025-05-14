# 6주차 | 테스트 및 기능 업그레이드

## 내가 찜한 영화.html 상세보기 기능 

![image](https://github.com/user-attachments/assets/96da4660-b980-457b-8857-ac5c02da9f6a)

->  '상세보기' 버튼 클릭 시 

![image](https://github.com/user-attachments/assets/96dc7b03-c94f-40c3-ab03-fe500445f8d0)

-> 영화 소개 페이지로 이동

![image](https://github.com/user-attachments/assets/77e45a6b-a0da-489b-bf03-dd51dc6d2d5f)

-> 영화 포스터 클릭 시 영화 예고편으로 이동

   <div class="movie-poster">
                        <img src="${movie.poster}" alt="${movie.title} 포스터">
                    </div>
                    <div class="movie-title">${movie.title}</div>
                    <div class="movie-actions">
                        <a href="${movie.url}" class="btn">상세보기</a>
                        <button class="btn remove-btn" data-id="${movieId}">찜 취소</button>
                    </div>


