### Hybrid_Recommendation_Modeling_using_Surprise
패션커머스 고객TPO(Time,Place,Occasion) 맞춤 추천모델링 프로젝트 

### 프로젝트 배경 
협업필터링 추천모델과 유저의 취향/TPO(Time, Place, Occasion)특성을 추가한 하이브리드 추천모델을 비교하여 유저별 다양한 맞춤추천모델링을 개발하고자 시작한 프로젝트입니다. 

### 프로젝트 가설 및 분석방법
(가설1) "패션커머스 데이터를 활용한 추천모델 중, 콘텐츠기반 필터링보다 협업필터링의 추천모델 성능이 더 좋을 것이다."
 - (분석방법) 각 모델의 RMSE, MAE 수치 비교

(가설2) "콘텐츠기반or협업필터링의 추천목록 보다 latent feature를 추가한 하이브리드(hybrid) 추천목록의 만족도가 실제 더 좋을 것이다."
 - (분석방법) 현실적으로 본 서비스의 유저의 실제 구매여부 데이터를 구할 수 없는 관계로, recall/precision/nDCG 등 일반적으로 추천목록의 유사도 성능을 파악하는 지표를 활용하였습니다. 다만, 실제 서비스에서는 유저의 반응도를 측정하여 테스트해볼 수 있을 것입니다. 

### 사용한 데이터
<데이터 주요 항목/설명>
- user_id: a unique id for the customer
- item_id: unique product id
- rating: rating for the product
- category: the category of the product
- rented for: purpose clothing was rented for

※데이터 출처: https://www.kaggle.com/rmisra/clothing-fit-dataset-for-size-recommendation?select=renttherunway_final_data.json

### 사용한 skill 및 지식 
- [“Build a Recommendation Engine With Collaborative Filtering”](https://realpython.com/build-recommendation-engine-collaborative-filtering/)
- ["Survey on Collaborative Filtering, Content-based
Filtering and Hybrid Recommendation System"](https://d1wqtxts1xzle7.cloudfront.net/59762468/10.1.1.695.642820190617-91457-z4s1rf.pdf?1560755155=&response-content-disposition=inline%3B+filename%3DSurvey_on_Collaborative_Filtering_Conten.pdf&Expires=1619766714&Signature=F-9q98BVtHDXVaC6ERT3seUgv5WHZ1LErrBIHN-5F7CXAEeAi5uxzh1wLvuxPTEGYvI41IVOd3mPKOi4m3i9HQSkxR5YOja9ZdglhzFo-K1bho-mpG6edrxeuFCGDA8lFJOlw9a5shZiBHIyQnHWcfI3Y4SKNri3bbo2PYQhu2nMiq7qxlATg6f1HLXqKIRbkVt-hOS6yt-fFaueN3I9-Du4gh9msqRzF8c3onca7fIRGFoTe0HIwWokS3VN4AzS-HQ2zedRg5KmE7f10hu7EhPQZISNzzwhR6zHHEchqFugV1VEeGgkQjNdzFnZkMBxdiTeyBHXgajj6vdDn5T0Wg__&Key-Pair-Id=APKAJLOHF5GGSLRBV4ZA)
- [“Hybrid recommendation approach”](https://www.math.uci.edu/icamp/courses/math77b/lecture_12w/pdfs/Chapter%2005%20-%20Hybrid%20recommendation%20approaches.pdf)
- [Python Surprise 라이브러리](https://surprise.readthedocs.io/en/stable/index.html)
- [hybrid_model_CF and Latent factor models](https://github.com/prakruti-joshi/Movie-Recommendation-System/blob/master/Code/hybrid_model.ipynb)

### 최종 기획안 
- [구글 문서](https://drive.google.com/file/d/1UrKqMLarciv59W-wdghh57_vGo-3IMSD/view?usp=sharing)

### 작업자
- 김현재 (hyeonjae.gim@gmail.com)
- 진행기간: 2021.2.22 - 2021.3.16
