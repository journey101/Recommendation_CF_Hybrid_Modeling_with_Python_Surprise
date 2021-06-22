## 파이썬 Surprise를 활용한 협업필터링, 하이브리드 추천모델링 (패션커머스 데이터 기반) 프로젝트

## ■ 프로젝트 배경 
협업필터링 추천모델과 유저의 취향/TPO(Time, Place, Occasion)특성을 추가한 하이브리드 추천모델을 비교하여 유저별 다양한 맞춤추천모델링을 구현하고자 시작한 프로젝트입니다. 

## ■ 프로젝트 가설 및 분석방법
(가설1) "패션커머스 데이터를 활용한 추천모델 중, 아이템기반 협업필터링(ex.knn-baseline-item-based)보다 SVD협업필터링의 추천모델 성능이 더 좋을 것"
 - (분석방법) 모델별 RMSE, MAE 수치 비교

(가설2) "아이템기반orSVD협업필터링의 추천목록 보다 latent feature를 추가한 하이브리드(hybrid) 추천목록 평가지표(recall, precision)가 더 좋을 것"
 - (분석방법) 모델별 추천목록의 recall/precision 수치 비교

## ■ 사용한 데이터
<데이터 주요 항목/설명>
- user_id: a unique id for the customer
- item_id: unique product id
- rating: rating for the product
- category: the category of the product
- rented for: purpose clothing was rented for

※[데이터 출처](https://www.kaggle.com/rmisra/clothing-fit-dataset-for-size-recommendation?select=renttherunway_final_data.json)

## ■ 결론 요약 / 배운 점 / 향후 보완하면 좋을 점

### [ 결론 요약 ]

### 1. 가설1 검정결과 : 아이템기반 모델(Knn-baseline_item-based)보다 SVDpp모델의 RMSE수치가 근소하게 낮음(성능이 좋음)

> KnnBaseline(item-based) RMSE: 0.718082 > SVDpp RMSE: 0.716266

 ==> 차이가 너무 근소하여 가설검정에 유의미하다고 보기 어려울 수 있다는 한계점.

![image](https://user-images.githubusercontent.com/70046278/119373992-02cd8e80-bcf4-11eb-9f24-8a4c93005073.png)

### 2. 가설2 검정결과: KnnBaseline(user-based)모델과 gridsearchCV로 조정한 SVDpp모델이 Recall값이 가장 높음.

> KnnBaseline(item-based) recall: 0.943002 < SVDpp(gridsearchCV) recall: 0.943309

 ==> 차이가 너무 근소하여 가설검정에 유의미하다고 보기 어려울 수 있다는 한계점.

![image](https://user-images.githubusercontent.com/70046278/119374495-9a32e180-bcf4-11eb-91da-2621feeb1d7f.png)


### [ 배운 점 ] 

### 1. 타겟 유저별 Hybrid 모델의 추천 목록 아이템 도출, 장점 파악
![image](https://user-images.githubusercontent.com/70046278/119374073-1842b880-bcf4-11eb-89cf-e0573a0cd964.png)

### 2. 데이터의 sparsity 가 높을 경우 SVD의 성능이 다른 모델에 비하여 생각보다 많이 높지 않을 수 있다는 점을 배움. 

### 3. 본 프로젝트에서는 nDCG 스코어에 대해서 정확히 이해하지 못하고 사용했던 부분이 있었는데, 다음 프로젝트(딥러닝 추천모델)에서 수식을 직접 코딩으로 구현해보는 과정을 통해 보완할 수 있었음.
※다음 프로젝트: [딥러닝을 활용한 이커머스 추천모델링](https://github.com/journey101/Ecommerce-Recommendation-System-with-DeepLearning-YoutubeAlgorithm)

### [ 향후 보완하면 좋을 점 ]
1. 유저의 구매고려사항에 대한 데이터 확보(해당 아이템을 살 때 고려하는 점의 우선순위 등)

2. 추천 시스템에 대한 유저의 취향 파악 (신선도 vs 유사도 비중을 어느 정도로 좋아하는지 등) 

3. 실제 유저가 반응한 유저행동데이터(구매/클릭/체험한 시간 등) 를 고려한 추천


## ■ 사용한 skill 및 지식 
- [“Build a Recommendation Engine With Collaborative Filtering”](https://realpython.com/build-recommendation-engine-collaborative-filtering/)
- ["Survey on Collaborative Filtering, Content-based
Filtering and Hybrid Recommendation System"](https://d1wqtxts1xzle7.cloudfront.net/59762468/10.1.1.695.642820190617-91457-z4s1rf.pdf?1560755155=&response-content-disposition=inline%3B+filename%3DSurvey_on_Collaborative_Filtering_Conten.pdf&Expires=1619766714&Signature=F-9q98BVtHDXVaC6ERT3seUgv5WHZ1LErrBIHN-5F7CXAEeAi5uxzh1wLvuxPTEGYvI41IVOd3mPKOi4m3i9HQSkxR5YOja9ZdglhzFo-K1bho-mpG6edrxeuFCGDA8lFJOlw9a5shZiBHIyQnHWcfI3Y4SKNri3bbo2PYQhu2nMiq7qxlATg6f1HLXqKIRbkVt-hOS6yt-fFaueN3I9-Du4gh9msqRzF8c3onca7fIRGFoTe0HIwWokS3VN4AzS-HQ2zedRg5KmE7f10hu7EhPQZISNzzwhR6zHHEchqFugV1VEeGgkQjNdzFnZkMBxdiTeyBHXgajj6vdDn5T0Wg__&Key-Pair-Id=APKAJLOHF5GGSLRBV4ZA)
- [“Hybrid recommendation approach”](https://www.math.uci.edu/icamp/courses/math77b/lecture_12w/pdfs/Chapter%2005%20-%20Hybrid%20recommendation%20approaches.pdf)
- [Python Surprise 라이브러리](https://surprise.readthedocs.io/en/stable/index.html)
- [hybrid_model_CF and Latent factor models](https://github.com/prakruti-joshi/Movie-Recommendation-System/blob/master/Code/hybrid_model.ipynb)

## ■ 최종 기획안 
- [구글 문서](https://drive.google.com/file/d/1UrKqMLarciv59W-wdghh57_vGo-3IMSD/view?usp=sharing)

## ■ 작업자
- 김현재 (hyeonjae.gim@gmail.com)
- 진행기간: 2021.2.22 - 2021.3.16
- 업데이트: 2021.5.24 
> (업데이트 사항)
> 
> (1) 주석 및 설명 수정. 
> 
> (2) f-measure, ndcg수치가 잘못되어 삭제. 
> 
> (3) 결론 / 배운 점 / 보완할 점 수정

---
# [update 사항(21.6.21):](Recommendation_CF_Hybrid_modeling_for_Fashion_update(210621).ipynb)
- ### 1. train : test 셋 비중 변경 후 모델 성능 변화.
 - 기존 6:4 -> 변경 5:5 
 - 변경 후, gridsearchCV(SVDpp)모델의 성능이 다른 모델에 비해 약 0.08수준 차이로 성능이 좋다고 나옴. 기존 학습에서는 0.001수준 차이로 성능이 높았음. 
 - ![#모델성능비교표_ 2021-06-21 오후 11 19 28__](https://user-images.githubusercontent.com/70046278/122779270-ad7f9f80-d2e8-11eb-8dcb-97eb33782c70.png)

- ### 2. 하이브리드 추천 알고리즘 계산방식 설명 추가. 
- ### 3. 하이브리드 추천 결과에서 (CF+CBF / Item-Similarity 결과가 뜨지 않는 에러 수정) 
 - 에러 원인: 함수 내에 'test'유저 아이디로 결과를 추출해야 하는데 train유저 아이디로 결과를 추출함. 
 - 해결된 결과:
 - ![#하이브리드모델2_추천결과_2021-06-21 오후 11 50 51](https://user-images.githubusercontent.com/70046278/122782797-fa18aa00-d2eb-11eb-8460-f5048932287d.png)


- ### 4. item:user = n:n 관계 확인 부분에서 user:item = 1:n 관계임을 확실히 보여주는 `sort_values()`코딩 셀 추가. 

- ### 5. SVD, SVDpp 성능이 크게 높지 않은 이유가, 충분한 크기의 데이터를 넣지 못해서 sparsity문제가 발생했을 수도 있겠다는 원인 추정. (이유: 코랩 런타임 한계로 데이터사이즈를 약 2만 Rows로 줄였기 때문)

> sparsity문제란?
> : ratings의 결측치는 모두 지웠기 때문에, 여기서 sparsity는 ratings의 missing value(결측치)가 아니라, user-item 으로 매칭한 행렬데이터에서 비어있는 공간을 의미하는 것으로 아이템:유저(N:N)관계에서 N이 충분히 크지 않다는 것을 의미. 즉, movielens처럼 아이템:유저의 N:N관계에서 N이 충분히 큰 데이터일수록 SVD, SVDpp의 성능이 좋다는 것을 의미함. 따라서, 코랩 런타임 한계로 데이터사이즈를 2만Rows크기로 줄인 점이 SVD모델 성능 저하의 원인일 수 있어보임.

- ### 6. gridsearchCV(SVDpp) 모델 하이퍼파라미터 설명 주석 추가

