# 오버 피팅을 잡기 위해 시도한 것들
가중치 규제 추가(매우 극적인 변화)

Dropout 추가(정확도는 올랐으나 오버피팅에 효과가 있는지는 모르겠다....)
# 정확도를 올리기 위해 시도한 것들
내 사진을 포함한 올라와있는 사진을 거의 한번씩 사용 해 본것 같고 그중에서 가장 정확도가 높고 실제로 보기에도 좋은 사진을 골랐다. 
일단 기존에 있던 모든 딥러닝 네트워크를 삭제하고 model.add(keras.layers.Dense(3, activation='softmax')) 를 사용해서 클래스 갯수만 정해준 다음

오버피팅에 효과가 있는 것들부터 추가하다 보니 자연스럽게 정확도가 올라갔다. 같은코드를 안의 숫자만 늘려서 반복하는 방식을 lms예제에서 보고 따라 했는데
이부분도 좋게 작용한듯 하다.




------------
2~3일동안 네트워크를 좋게 만들어서 정확도를 높이기 위해서 시도했는데 부질없는 짓이였다..
lms 안에있는 내용으로만 보면 그게 가능한것 처럼 적혀있지만 그 어느것도 전혀 도움이 되지 않았고. 
정확도를 올리고 오버피팅을 막기 위해 검색을 하던중

https://wikidocs.net/61374

https://junstar92.tistory.com/102

https://studyfield.tistory.com/652 

이 세가지 글을 보게 되었고 이를 딥러닝 네트워크에 적용하여 극적인 결과를 얻어 내었다.

다음에는 LMS에만 묶여 있지 않고 빠르게 구글의 바다속으로 떠나자;;
그리고 fit()에서 validation_split=0.3 사용하여 정확도의 정당성(?) 도 추가했는데 정확히 이것이 어떻게 도대체 왜 정확도에 영향을 주는지는 잘 모르겠다..
# 코드관련
정확도 올리는 과정이 진척이 안되서 화가나고 있는차에 자꾸만 눈에 밟히는 반복되는 코드만 조금 수정하였다.
