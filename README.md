![fdsgdfgs](https://github.com/shinmg1215/smg031215/assets/145413860/bfc8dd99-1a2c-43e1-8021-5fec66a09654)
# MobileBERT를 활용한 pc 게임 평점 분석
<img src="https://img.shields.io/badge/pytorch-%23EE4C2C.svg?&style=for-the-badge&logo=pytorch&logoColor=white" /> <img src="https://img.shields.io/badge/pycharm-%23000000.svg?&style=for-the-badge&logo=pycharm&logoColor=white" />
<img src="https://img.shields.io/badge/python-%233776AB.svg?&style=for-the-badge&logo=python&logoColor=white" />

### 1.1 문재 정의
전세계 사람들이 즐기는 pc게임중 역대 최고의 pc게임별 평점과 리뷰를 분석할려고 한다.

### 1.2 pc 게임 리뷰의 영향력
게임은 전세계 어디서든 즐길수 있는 하나의 스포츠다. fps, aos , rpg, mmorpg 등 
다양한 종류가 있으며 현대 사회 에서는 e스포츠 라는 명칭으로 하나의 스포츠로 자리 잡았다.
그러므로 전세계 역대 최고의 pc게임의 평과와 리뷰를 분석하는것은 정말 의미있는 분석 일것이다.

![스크린샷 2024-05-14 113430](https://github.com/shinmg1215/smg031215/assets/145413860/93638670-0674-48dc-896d-b6c659c1ec7e)

## 2. 데이터
## 2.1 원시 데이터 
역대 최고의 pc 게임 에 평점과 리뷰를 분석한 데이터

![스크린샷 2024-04-30 114104adsdsa](https://github.com/shinmg1215/smg031215/assets/145413860/280184e4-cccb-48d6-acfb-d00886215775)

(https://www.kaggle.com/datasets/argaadya/best-pc-of-all-times-metacritic-game-review/data)
## 2.2 추출한 데이터
대량의 데이터에서 평점 및 리뷰를 추출한다. (30769건)


![Figure_1](https://github.com/shinmg1215/smg031215/assets/145413860/9fd7a3ed-07b2-44c8-9914-14f6bb282390)

위에 보이는 그래프는 게임별 리뷰 개수를 알수 있다

### 2.3 추출한 데이터에 대한 탐색적 데이터 분석


| 게임 명  | 리                                                                                  |
|--------|-------------------------------------------------------------------------------------|
| overwatch      | 이것은 좋은 게임이다. 좋은 협동심, 멀티러. 매주 전리품 상자와 최고의 스킨을 획득해야 합니다.                                       |
| team-fortress-2  | 지금까지 플레이할 수 없는 가장 균형 잡히고 즐겁고 재미있는 FPS입니다. 이 게임을 소유하지 않았거나 이 게임을 한 번도 해본 적이 없다면 당신은 스스로를 '게이머'라고 칭할 자격이 없습니다.            |
| grand-theft-auto-v | 아직도 재생 중입니다. 이 게임의 끝없는 콘텐츠 양은 정말 놀랍습니다. 최근의 스턴트 미션은 많은 새로운 생명을 불어넣었습니다. 싱글 플레이어는 완벽했습니다.                                |




## 3. 학습 데이터
### 3.1 첫 번째 학습 데이터
첫 번째 학습 데이터는 전체 리뷰 데이터 30000만건 이상을 추출하여 만들었다.

![스크린샷 2024-05-28 115754saddsa](https://github.com/shinmg1215/smg031215/assets/145413860/559cc3e3-08c0-4a87-8329-4ddbda077dbb)






### 3.2  소스코드 데이터 추출 값값

![스크린샷 2024-05-31 104952](https://github.com/shinmg1215/smg031215/assets/145413860/272f44eb-5df3-4968-b103-daee5277805b)




![스크린샷 2024-05-31 10504459198](https://github.com/shinmg1215/smg031215/assets/145413860/5606d9c5-4947-4e9a-9b10-71ee1e8640ac)



### 3.3  소스코드 



import pandas as pd
import matplotlib.pyplot as plt

file_path = r"C:\Users\user\Downloads\game_review.csv (2)\game_review.csv"

 with open(file_path, 'rb') as f:
     result = chardet.detect(f.read())

#print("추정된 인코딩:", result['encoding'])

data = pd.read_csv(file_path, encoding='Windows-1252')

data.rename(columns={'game': 'GameName'}, inplace=True)

#print(data['GameName'].value_counts()[:20])
data['GameName'].value_counts()[:20].plot(kind='bar')
plt.show()




### 4느낀점 및 배운점

어렵긴 했지만 그래도 재미있었다

