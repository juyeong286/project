# 6주차 | 테스트 및 기능 업그레이드

## 내가 찜한 영화.html 상세보기 기능 

![image](https://github.com/user-attachments/assets/96da4660-b980-457b-8857-ac5c02da9f6a)

->  '상세보기' 버튼 클릭 시 

![image](https://github.com/user-attachments/assets/96dc7b03-c94f-40c3-ab03-fe500445f8d0)

-> 영화 소개 페이지로 이동

![image](https://github.com/user-attachments/assets/77e45a6b-a0da-489b-bf03-dd51dc6d2d5f)

-> 영화 포스터 클릭 시 영화 예고편으로 이동

```bash
   <div class="movie-poster">
                        <img src="${movie.poster}" alt="${movie.title} 포스터">
                    </div>
                    <div class="movie-title">${movie.title}</div>
                    <div class="movie-actions">
                        <a href="${movie.url}" class="btn">상세보기</a>
                        <button class="btn remove-btn" data-id="${movieId}">찜 취소</button>
                    </div>
```

## 홈페이지 이동 업그레이드

![image](https://github.com/user-attachments/assets/f8bab9d8-3fd4-417b-bfd8-4dee6a2107d5)

-> 'MOVIE RECIPE' 글자 클릭 시 

![image](https://github.com/user-attachments/assets/41ebd86c-6006-47a8-97df-bfc1acc3d204)

-> 첫 홈페이지로 이동

![image](https://github.com/user-attachments/assets/cab793a6-58bf-42c6-b652-e31746dbef7a)

-> 'MOVIE RECIPE' 글자 클릭 시 

![image](https://github.com/user-attachments/assets/3c94adfb-e9c2-4c90-b8cf-002228d44eb8)

-> 메인 홈페이지로 이동

```bash
  <h1><a href="사이트-2.html" style="text-decoration: none; color: inherit;">MOVIE RECIPE</a></h1>
```




