# 3주차 전체적인 틀 구상

[코드]

```bash
  <!DOCTYPE html>
<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>영화 추천 사이트</title>
    <style>
        /* 기본 스타일 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Noto Sans KR', sans-serif;
        }
        
        body {
            background-color: #141414;
            color: #fff;
            line-height: 1.6;
        }
        
        header {
            background-color: rgba(0, 0, 0, 0.8);
            padding: 20px 0;
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .container {
            width: 90%;
            max-width: 1200px;
            margin: 0 auto;
        }
        
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            color: #e50914;
            font-size: 1.8rem;
            font-weight: bold;
        }
        
        .menu {
            display: flex;
            list-style: none;
        }
        
        .menu li {
            margin-left: 20px;
        }
        
        .menu a {
            color: #fff;
            text-decoration: none;
            transition: color 0.3s;
        }
        
        .menu a:hover {
            color: #e50914;
        }
        
        .hero {
            height: 70vh;
            background-image: linear-gradient(rgba(0, 0, 0, 0.7), rgba(0, 0, 0, 0.7)), url('https://via.placeholder.com/1920x1080');
            background-size: cover;
            background-position: center;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            margin-bottom: 50px;
        }
        
        .hero-content {
            max-width: 800px;
        }
        
        h1 {
            font-size: 3rem;
            margin-bottom: 20px;
        }
        
        p {
            font-size: 1.2rem;
            margin-bottom: 30px;
        }
        
        .btn {
            display: inline-block;
            background-color: #e50914;
            color: #fff;
            padding: 12px 24px;
            border-radius: 4px;
            text-decoration: none;
            font-weight: bold;
            transition: background-color 0.3s;
        }
        
        .btn:hover {
            background-color: #f40612;
        }
        
        .movies-section {
            padding: 50px 0;
        }
        
        h2 {
            font-size: 2rem;
            margin-bottom: 30px;
            padding-bottom: 10px;
            border-bottom: 2px solid #e50914;
            display: inline-block;
        }
        
        .movie-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 30px;
            margin-top: 30px;
        }
        
        .movie-card {
            background-color: #222;
            border-radius: 8px;
            overflow: hidden;
            transition: transform 0.3s, box-shadow 0.3s;
            cursor: pointer;
        }
        
        .movie-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
        }
        
        .movie-poster {
            width: 100%;
            height: 370px;
            object-fit: cover;
        }
        
        .movie-info {
            padding: 15px;
        }
        
        .movie-title {
            font-size: 1.2rem;
            margin-bottom: 8px;
        }
        
        .movie-genre {
            color: #aaa;
            font-size: 0.9rem;
        }
        
        .rating {
            color: #ffd700;
            margin-top: 8px;
            display: flex;
            align-items: center;
        }
        
        .star {
            margin-right: 5px;
        }
        
        .genre-filter {
            margin-bottom: 30px;
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }
        
        .genre-btn {
            background-color: #333;
            border: none;
            color: #fff;
            padding: 8px 16px;
            border-radius: 20px;
            cursor: pointer;
            transition: background-color 0.3s;
        }
        
        .genre-btn:hover, .genre-btn.active {
            background-color: #e50914;
        }
        
        footer {
            background-color: #000;
            color: #777;
            padding: 30px 0;
            text-align: center;
            margin-top: 50px;
        }
        
        .social-links {
            margin-top: 20px;
        }
        
        .social-links a {
            color: #777;
            margin: 0 10px;
            font-size: 1.2rem;
            transition: color 0.3s;
        }
        
        .social-links a:hover {
            color: #e50914;
        }
        
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.8);
            z-index: 999;
            align-items: center;
            justify-content: center;
        }
        
        .modal-content {
            background-color: #222;
            width: 90%;
            max-width: 800px;
            border-radius: 8px;
            overflow: hidden;
            position: relative;
        }
        
        .close-btn {
            position: absolute;
            right: 15px;
            top: 15px;
            color: #fff;
            font-size: 1.5rem;
            cursor: pointer;
            z-index: 10;
        }
        
        .movie-details {
            display: flex;
            flex-direction: column;
        }
        
        .movie-header {
            display: flex;
            padding: 20px;
        }
        
        .movie-poster-lg {
            width: 200px;
            border-radius: 8px;
            margin-right: 20px;
        }
        
        .movie-header-info {
            flex: 1;
        }
        
        .movie-description {
            padding: 0 20px 20px;
        }
        
        @media (max-width: 768px) {
            .movie-grid {
                grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            }
            
            .movie-header {
                flex-direction: column;
            }
            
            .movie-poster-lg {
                width: 100%;
                margin-right: 0;
                margin-bottom: 20px;
            }
        }
    </style>
</head>

    <section class="hero">
        <div class="hero-content">
            <h1>MOVIE RECIPE</h1>
            <p>당신의 취향에 맞는 최고의 영화들을 발견하세요. 장르, 감독, 배우 등 다양한 기준으로 영화를 찾아보세요.</p>
            <a href="#movies" class="btn">영화 추천 보기</a>
        </div>
    </section>

```
![Image](https://github.com/user-attachments/assets/0df63486-5fbd-4f70-abc3-3849f3a682fa)
