# ONservice
ON고지신공모전 유저소구 관련 파이썬 데이터분석 코드입니다.
농수산물 데이터 분석
개요
이 프로젝트는 자연어 처리(NLP) 기술을 사용하여 농수산물 데이터에 대한 사용자 요청을 분석하여 통찰력을 추출하고 주요 동향을 파악합니다. 주요 초점은 데이터 요청을 분류하고 사용자 행동에서 의미 있는 패턴을 찾아내는 것입니다.

특징
텍스트 전처리:

한국어 텍스트 처리를 위해 Mecab을 사용한 토큰화.
불용어 제거 및 희귀/빈번 단어 필터링을 통해 데이터 품질 향상
주제 모델링:

데이터에서 숨겨진 주제를 추출하기 위해 **Latent Dirichlet Allocation(LDA)**을 적용했습니다.
모델의 해석 가능성과 적합성을 향상시키기 위해 매개변수를 최적화했습니다.
클러스터링:

고유한 사용자 요청 유형을 식별하기 위해 K-평균 클러스터링을 사용하여 그룹화된 텍스트 데이터입니다.
실루엣 점수 및 데이비스-볼딘 지수와 같은 측정항목을 사용하여 클러스터를 평가했습니다.
시각화:

자주 사용되는 용어를 시각화하기 위해 단어 구름을 만들었습니다.
주제 모델의 대화형 탐색을 위해 PyLDAvis를 사용했습니다.
평가 지표:

Coherence Score 및 Perplexity를 사용하여 주제 품질을 평가했습니다.
사용된 기술
프로그래밍 언어: Python
라이브러리:
데이터 처리를 위한 pandas
텍스트 전처리를 위한 konlpy 및 Mecab
주제 모델링을 위한 gensim
클러스터링 및 평가를 위한 scikit-learn
시각화를 위한 wordcloud 및 pyLDAvis
주요 결과
일관성 점수: 0.5641(잘 정의되고 해석 가능한 주제를 나타냄)
복잡성: -2.6300(데이터에 합당한 적합성을 나타냄).
확인된 주요 주제:
애완 동물 및 가축 통계.
시장 동향 및 인증.
조리법 및 성분 데이터.
동물에 관한 정책 및 연구 자료.
지역별 생산 및 애완견 데이터입니다.
설치 및 설정
1. 저장소 복제
bash
코드 복사
git clone https://github.com/uzzain/ONservice/agricultural-marine-data-analysis.git
cd agricultural-marine-data-analysis
2. 필수 라이브러리 설치
requirements.txt(사용 가능한 경우)를 사용하거나 수동으로 설치하십시오.

bash
코드 복사
pip install pandas konlpy gensim scikit-learn wordcloud pyLDAvis
3. Mecab 설치 및 구성
Mecab-ko-for-Google-Colab 저장소의 지침에 따라 한국어 텍스트 처리를 위해 Mecab을 설정하세요.

용법
데이터 전처리:
텍스트를 정리하고, 토큰화하고, 단어를 필터링합니다.
주제 모델링을 수행합니다.
조정된 매개변수를 사용하여 LDA 모델을 실행합니다.
결과 평가:
일관성 점수와 Perplexity를 사용하여 모델 품질을 평가합니다.
결과 시각화:
워드클라우드와 PyLDAvis 시각화를 생성합니다.
명령어 예시
전처리:

python
코드 복사
from konlpy.tag import Mecab
mecab = Mecab()
tokens = mecab.nouns("텍스트 데이터 예시")
LDA 모델 교육:

python
코드 복사
from gensim.models import LdaModel
lda_model = LdaModel(corpus=corpus, id2word=dictionary, num_topics=5, passes=10)
심상:

python
코드 복사
import pyLDAvis.gensim_models
pyLDAvis.enable_notebook()
pyLDAvis.display(pyLDAvis.gensim_models.prepare(lda_model, corpus, dictionary))
파일 구조
bash
코드 복사
.
├── data/                     # Input data files
├── results/                  # Outputs such as visualizations and model results
├── notebooks/                # Jupyter Notebooks for analysis
├── scripts/                  # Python scripts for preprocessing and modeling
├── README.md                 # Project overview and instructions

라이센스
이 프로젝트는 MIT 라이선스에 따라 라이선스가 부여됩니다. 자세한 내용은 'LICENSE' 파일을 참조하세요.
