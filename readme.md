# JPX Tokyo Stock Exchange Prediction

- 목적: kaggle에서 진행되는 대회인 JPX Tokyo Stock Exchange Prediction에 어떤 결과물들이 있는지 보고, 학습한다.
  

- 대회 주소: https://www.kaggle.com/competitions/jpx-tokyo-stock-exchange-prediction

- 대회 설명: 금융 시장 분석 및 투자 전략 수립을 위한 JPX 도쿄 증권 거래소의 주가 예측 모델을 만들고, 기대 수익률에 대한 주식의 순위를 매긴다.


- 평가
  - 일별 spread에 대한 Sharpe Ratio에 따라 평가
  - 특정 날짜의 각 주식의 순위를 매긴다. 상위 200개 주식을 매수하고 하위 200개 주식을 매도한 뒤, 순위에 따른 가중치를 붙여 다음 날 주식을 매입하여 그 다음날 매도했다고 가정하여 총 수익률을 계산한다.

- 제출: 제공된 python 시계열 api를 사용하여 제출해야 한다.
~~~python
import jpx_tokyo_market_prediction
env = jpx_tokyo_market_prediction.make_env()   # initialize the environment
iter_test = env.iter_test()    # an iterator which loops over the test files
for (prices, options, financials, trades, secondary_prices, sample_prediction) in iter_test:
    sample_prediction_df['Rank'] = np.arange(len(sample_prediction))  # make your predictions here
    env.predict(sample_prediction_df)   # register your predictions
~~~

- 일정
  - 2022.04.04. 대회 시작
  - 2022.06.28. 대회 참가 마감
  - 2022.06.28. 팀 합병 마감
  - 2022.07.05. 최종 제출 마감
  - 2022.10.07. 대회종료, 우승자 발표


- 요구 조건
  - Notebook을 통해 제출해야 함.
  - CPU Notebook <= 9 hours run-time
  - GPU Notebook <= 9 hours run-time
  - 인터넷 연결 비활성화
  - 사전 훈련된 모델을 포함하여 자유롭게 공개적으로 사용 가능한 외부 데이터가 허용
  - 제출 파일의 이름은 API가 생성하는 submission.csv. 
  
