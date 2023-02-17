# 한국 음악시장 성공요인 분석

## 프로젝트 주제

  - 한국 음악시장 성공요인 분석
    - 어떠한 요인을 통하여 한국 음원시장에서 성공을 할 수 있는지 분석
    - 또한 이제까지의 성공요인과 데이터가 많아지고 발전한 지금의 음원시장의 성공요인 차이를 분석

## 프로젝트 기간

  - 2022.11.26 ~ 2022.12.10
  
## 프로젝트 목표

  1.	선행 연구와는 다른 점을 통하여 음원 성공요인파악
  2.	성공 요인을 토대로 모델링 후 예측
  3.	예측 결과를 통하여 비즈니스 의사결정에 도움


## 프로젝트 분석 방법

  1.	EDA를 통하여 음원 성공요인 및 한국 음원 시장 분석
  2.	모델링을 통한 음원의 인기도 파악
  3.	음원의 인기도에 영향미치는 요인 파악
  4.	그 요인이 실제로 영향을 미치는 지 검증
  5.	데이터와 데이터 외적인 요인 비교를 통하여 음원 인기 요인 분석
  6.	모델링한 결과로 예측을 통하여 실제로 음원에 영향을 미치는 지 파악

## 참고 자료
  
  - 디지털 시대, 음반의 흥행요인 (Who can be a deus ex machina in the industry ?)
    - https://scienceon.kisti.re.kr/srch/selectPORSrchArticleOrgnl.do?cn=DIKO0013688578
  - 대중음악 음원의 흥행요인에 관한 연구
    - https://scienceon.kisti.re.kr/srch/selectPORSrchArticleOrgnl.do?cn=DIKO0014911103
  - 한국콘텐츠진흥원_2020년도_음악_산업백서
    - https://www.data.go.kr/data/15090664/fileData.do
    
## 사용 데이터 

   - 스포티파이 api 
        - https://developer.spotify.com/
        - 스포티파이 api를 활용하여 직접 가수의 Audio Features를 크롤링할 수 있다.
        - 2010년부터 2022년간 한국 시장에서 상위 1000개 곡을 크롤링(크롤링 날짜 : 11월 12일)
            - track_with_audio_features_2010_2022.csv로 저장 후 사용

   - 각 나라별 선호 장르
        - https://www.kaggle.com/datasets/marshalll3302/favorite-music-genres-by-country
            - 캐글 dataset에서 구한 데이터셋으로 각 나라별로 어떠한 장르를 선호하고 있는지를 나타낸 데이터
            - clean.csv
               
   - 온라인에서 Kpop음원 가격 정보
        - https://www.kaggle.com/datasets/ericwan1/kpop-merchandise-prices?select=all_shops.csv
         
     
   - 한국인 사용 OTT 순위(자주 사용하는 OTT 순위)
        - https://stat.kisdi.re.kr/kor/tblInfo/TblInfoListResult.html?vw_cd=MT_ATITLE&siteGb=SITE001
        - 미디어 통계포털
        
   - 스포티파이 데이터
       - https://www.kaggle.com/datasets/dhruvildave/spotify-charts
       - 각 날짜별 stream데이터를 활용하기 위해서 사용
       - 총 데이터가 4GB라서 따로 정제해서 사용
       - 2021년 3월부터 2021년 11월까지 각 날짜별 스트리밍 수와 노래 제공
       - 위에서 직접 수집한 스포티파이 데이터와 병합을 통해 사용
       - 따로 전처리하여 clean_stream.csv로 저장하여 사용
       
## 결론

- 선행연구에서는 음원의 성공요인에 장기적인 요인으로는 제작사의 역량과 단기적인 요인으로는 유통사의 역량이 크다고 밝혔다. 또한 메이저 기획사일 수록 음원이 성공을 하며 팬덤이 클 수록 성공을 한다는 결과를 보여주고 있다.
- 하지만 선행연구와는 다르게 음악적 특성, 키워드 검색량, 팬덤이 3가지를 통하여 위의 원인과 더불어 음악적 특성에도 더 가중치가 많이들어가는 성공에 더 영향을 많이 주는 특성들이 있으며 키워드 검색량과 스트리밍 횟수가 비슷하게 진행되고, 또한 특정 프로그램(쇼미더머니 등)에서 만드는 음반 또한 가수의 인지도와는 다르게 성공을 하는 케이스들을 보여주었다.
- 위의 결과에 팬덤의 인기도 또한 음원의 성공에 큰 영향을 미친다고 판단하였고, 만든 분류 모델로 예측을 해본 결과 음악 외적요인(팬덤 및 발매 연도)를 제외하고 모델링한 결과와 포함하고 모델링한 결과에서의 예측값이 차이가 나는 것을 통하여 음악적으로 전부 되는 것이 아니고 음악 외적요인도 크게 작용하는 것을 확인 할 수 있었다.
