# 컨트리뷰션 가이드

# 컨트리뷰션 가이드

'2021 오픈 컨트리뷰션 아카데미'의 '딥러닝(케라스) 실용 예제 구축' 프로젝트 진행을 위한 가이드

# 컨트리뷰션 목적

케라스 공식 홈의 케라스 예제(Keras Examples)에 대한

- 한글 설명 작성
- 이론적인 배경 설명 작성
- 새 예제 추가
- 작성한 결과를 책으로 출판

# 진행 일정

- 2021/8/7(토) : 발대식
- 2021/8/7(토) ~ 10/22(금) : 컨트리뷰션 진행
- 2021/10 : 온라인 컨텐츠 제작, 온라인 컨퍼런스 개최
- 2021/10 : 결과보고서 제출
- 2021/10/23(토) : 최종 심사 및 성과 발표회
- 2021/11 : 집필 진행
- 2021/11 : 지역 스프린트
- 2021/12 : 시상식

# 구체적인 액션 아이템

- 대상 예제 선정
- 대상 예제에 대한 설명, 이론적 배경 작성
    - commit, PR, merge(keras-docs-ko)
- 신규 예제 작성
    - commit, PR, merge(keras-io)
- 온라인 컨퍼런스
    - 온라인 컨텐츠 작성
    - 온라인 발표
- 책 집필
    - 책을 위한 내용 작성
    - 기타 사항 작성

# 작업 방법 상세 - kreas-docs-kr

케라스 공식 홈의 예제 페이지([https://keras.io/examples/](https://keras.io/examples/))에서 예제들을 살펴보고

예제 현황 문서([https://docs.google.com/spreadsheets/d/1AqPGDcMo9cr02JqK23ntSBGCk-dOTvXtR6gtNlqmA0M/edit#gid=0](https://docs.google.com/spreadsheets/d/1AqPGDcMo9cr02JqK23ntSBGCk-dOTvXtR6gtNlqmA0M/edit#gid=0))의 신청 컬럼에 이름을 적는다.

같은 예제에 신청자가 여러명이면

- 신청자 들 간에 합의
- 다시 합의
- 다시 합의

1인 최소 4개를 권장.

- 총 100 개 정도
- 전체를 다 할 필요는 없다.
- 컨트리뷰터 17명+2명.

# 예제 설명과 이론적 배경 설명을 잘하려면

기존 에제들이 아주 깊은 내용 보다는 케라스 튜토리얼의 일부 정도의 수준.

하지만 몇 예제들은 그래도 깊이 혹은 이론적인 사항을 배경으로 하고 있다.

후배가, 후임이 와서 그 예제를 물어 볼때 **설명해 주듯이** 예제 설명을 적어 나가면 된다.

원 설명이 좋으면 그냥 번역으로도 좋다. 하지만 단순 번역은 대충 아쉽다.

일단 실행되는 코드에 대하여 익숙해 져야 하고, 이론적인 사항이 있으면 공부해야 하고,

**예제에 언급이 안된 사항이나 따로 공부한 것**이 있으면 그걸 이론적인 배경으로 추가하면 된다.

문장 작성에 대한 가이드라인은 '케라스 공식 문서 한국어판'의 번역 가이드라인([https://github.com/keras-team/keras-docs-ko#번역-가이드라인](https://github.com/keras-team/keras-docs-ko#%EB%B2%88%EC%97%AD-%EA%B0%80%EC%9D%B4%EB%93%9C%EB%9D%BC%EC%9D%B8)) 정도로.

원 예제의 문서 구조를 유지하는게 편하지만, 필요 있다면 섹션을 추가하거나 구조를 변경할 수도 있다.

코드가 지저분 하다면 수정할 수도 있고. 이럴 경우 keras-io에 직접 PR 할 수도 있겠다.

어짜피 단순 번역이 아니라서 원 예제와의 동기화는 현재 고려하고 있지 않다.

# 예제 설명 작성 상세

## 스텝 1. 대상 파일 구조와 결과물 이해

파일 구조

```
project_root/
    README.md : 케라스 한글 문서 홈
    examples/
        README.md : 케라스 한글 예제 홈
        contribution_guid.md : 본 문서
        vision/
            image_classification_from_scratch.py : 1개 예제에 대한 1개의 py파일
            ...
        audio/
        .../

```

최종적으로 py 파일을 추가할 것이다. 이 파일은 노트북 파일 ipynb 파일에서 스크립트를 통해 자동 생성된다. 이 자동 생성은 본 프로젝트 말에 한 번에 처리할 것이다.

그렇다면 작업한 결과물은 노트북 파일 ipynb이다.

## 스텝 2. 대상 예제를 colab에서 열기

colab은 google에서 제공하는 jupyter 서비스 이름이다. 사용을 위해서는 google 계정이 필요하다. gmail.com에서 가서 메일 계정 생성하면 그 계정이 google 계정이다.

chrome 사용을 강하게 권장한다. chrome에서 로그인하고 Keras Examples 페이지에서 대상 예제를 클릭해서 예제 페이지로 이동한다.

상단의 'View in Colab'을 클릭한다.

Colab이 아닌 별개의 환경에서 작업해도 무방하다. 그런데 굳이...

## 스텝 3. 한글 해설 달기, 이론 설명

오픈된 노트북에서 실제 작업을 진행한다. 해설을 달고, 코드도 개선하고, 배경 이론도 추가하고.

작업이 완료되고 나면 코드를 실행한다. 그리고 그 결과가 수정안된 노트북의 실행결과와 같은 지 비교한다. 별개의 테스트코드가 없기 때문에 실행하여 확인하는 것은 엄청나게 **중요**하다. 리뷰하거나 머징할때에도 이를 확인할 방법은 없다. 오직 작업자의 성실에 의존해야 하는 사항이다. 다른 모든 것은 어떻게든 협업이 가능하고 도움이 가능하다. 그런데 이 동작 확인은 작업자에게 의존적이다.

## 스텝 4. 작업노트북 다운로드

Colab에서 '파일' > '다운로드' > '.ipynb 다운로드'를 클릭하여 작업자 컴으로 노트북을 다운르도 받는다.

## 스텝 5. branch 생성, 작업 내역 작성, 노트북 추가

프로젝트 [https://github.com/keras-team/keras-docs-ko](https://github.com/keras-team/keras-docs-ko) 를 git으로 checkout한다.

본 설명에서는 image_classification_from_scratch.py를 작업 대상으로 한다.

새로운 branch image_classification_from_scratch를 만든다. 혹 기존에 이미 branch가 있으면 branch로 변경한다.

```
$ git branch image_classification_from_scratch

```

작업 대상 예제 파일과 같은 폴더에 ipynb 파일을 추가한다.

```
keras-docs-ko/
    examples/
        vision/
            image_classification_from_scratch.ipynb

```

같은 위치에 image_classification_from_scratch.md 이름으로 파일을 추가하고, 이 문서에 작업한 내역을 작성한다.

```
keras-docs-ko/
    examples/
        vision/
            image_classification_from_scratch.ipynb
            image_classification_from_scratch.md

```

## 스텝 6. add, commit, push

add하고 commit하고 push한다.

```
$ git add *
$ git commit -m "example:image_classification_from_scratch : init add"
$ git push
```

커밋 메시지는 "example:"로 시작하고 작업 대상 image_classification_from_scratch을 붙여서 시작한다.

```
example:image_classification_from_scratch: 오타 수정
example:image_classification_from_scratch: 버그 픽스
example:image_classification_from_scratch: 설명 추가
```

참고로 online git 개발 환경 [https://gitpod.io/](https://gitpod.io/) 사용을 추천한다. 사용자 컴에 무언가 별도로 설치하지 않아도 작업이 가능하다.

## 스텝 7. PR(Pull Request) 생성

TODO : add details

## 스텝 8. 결과물 리뷰

TODO : add details

## 스텝 9. Merging

TODO : add details

# 작업 내역 문서 - keras-docs-kr

## Template

[working_history.md](https://vscode-remote+green-coyote-vk8zh7dc.ws-us13.gitpod.io.vscode-resource.gitpod.io/workspace/keras-docs-ko/examples/working_history.md)

## 작성 기준

이 문서의 목적은 리뷰이다. 리뷰를 할 때 어떤 내용이 작업되었는 지를 파악하지 못하면 리뷰가 불가능하다. 리뷰어는 코드가 아닌 문서를 먼저 읽고 내용이 파악되지 않으면 문서 보완을 먼저 요청한다. 이 말은 문서 내용이 작업 내용을 파악하기에 적당하지 않으면 리뷰가 진행되지 않고 결과적으로 merging되지도 않으며 작업한 결과가 체택되지 않는 다는 것이다.

문서를 통해 작업 내용을 파악하고 그 결과물을 검토하는 것은 쉽지만, 결과물만 보고 무엇이 변경되고 어떤 작업을 했는지 파악하는 것은 극히 어렵다.

문서의 목적은 리뷰를 위한 작업 내용 파악이다.

문서의 템플릿은 존재한다. 하지만 그 포멧이나 기술 방법은 작업 내용 파악이라는 목적에 부합하면 어떻더라도 문제되지 않는다.

# 작업 방법 상세 - keras-io

TODO : add details

작업 단계

1. 예제 선정
2. 라이센스 구하기
3. 예제 작업
4. 머징 요청
5. 리뷰
6. 필요시 보완
7. 머징

## 단계 1. 예제 선정

# 기존 예제 개선

기존 예제의 코드 수준이나 설명이 안타까운 것들도 있다. 새로 작성하는 한글 작업물에서는 코드와 설명을 개선해서 햇으면 싶고, 원본을 개선해서 PR을 날리는 것으로 하면 더 좋을 듯.

# 온라인 컨테츠 작성 상세

예제에 관한 이론 및 코드 설명 동영상 콘텐츠 제작

- 이론: 25분
- 코드설명: 25분
- 추가 솔루션설명: 10분

의무는 아니다. 하지만 온라인 발표 자료 만들어 보고 발표 해보는 것이 정말 크게 도움이 된다. 작업한 결과물, 이미 이해하고 익숙해져 있는 것, 자료 만들어서 발표해 보자.

참고 : 2020년의 KLD(Keras Learning Day) : [http://aifactory.space/kld](http://aifactory.space/kld)

# 작업 결과 검토(리뷰) 기준

작업 결과에 대한 리뷰를 진행하고 다음과 같은 기준으로 보완을 요청한다.

- 작업 내역 문서 여부 : 검토 대상 작업이 무엇인지 파악이 안되면 검토를 못한다.
- 실행 : 코드 실행이 안되면 곤란하다. 아주 곤란하다.
- 오타 : 설명이나 코드에 오타 있으면 좀 그렇다.
- 이해도 : 쉽게 이해 되었으면. Keras를 공부하는 이에게 도움이 되었으면.
- 완성도 : 내용 수정 없이 단순 에디팅 정도로 책 집필에 사용되면 좋겠다.

배제된 기준

- 일관성 : 다수의 작업자들에게 엄격한 일관성을 요청하기는 어렵다. 그것도 짧은 기간에
- 영문/한글 사용 : 기준 용어집이 있으면 좋겠지만, 이것 작성도 만만치 않다. 책 집필 시에 한번에 정리하는 것이 어떨가 싶다.

# 책 집필 상세

TODO : add details

# 멘토... 멘티...

## 컨트리뷰션

모든 것은 멘티의 노력으로 이루어 진다.

멘토는 단지 멘티를 도와줄 뿐이다. 감독이라 관리 아니다.

멘토는 마스터가 아니다. 당연하다. 잘 모를 수도 있다. 모든걸 다 할 수도 없다. 이 문서 만드는 것도 벅차다.

의견을 모으고, 협의를 유도하고, 동기를 유발하고, 조금 조화롭게 하는게 멘토의 역할.

가끔은 혹은 어쩌다 기술적인것 도움이 될 수도 있을지 모르겠고.

컨트리뷰션은 자신을 발전 시킨다. 결과물 뿐 아니라 그 작업, 작업하기 위한 협력 과정이 개발자의 살이 된다. 컨트리뷰션은 자발적일 수 밖에 없다.

## 부족한 멘토에게 도움을

모든 작업이 치밀하게 계획되어 진행 될 수 없다. 처음 부터 잘 준비해서 진행하면 좋겠지만 그렇지 않은게 인생이다. 팀으로 공동 작업을 하고 다수의 의견을 반영하다 보면 무언가 바뀌고 개선된다. 이 와중에 다소의 비효율이 발생한다. 하지만 이를 통해 서로 성장한다. 서로 존중하고 도와주었으면 한다.

최종 마무리 단계에서는 아무래도 일관성을 고민하게 되고, 이때 부가적인 작업이 있을 수도 있겠다. 많은 도움을 요청드린다.

## 멘토 활용

회사의 일로 하는게 아니다. 자발적인 컨트리뷰션이다. 관리대상도 아니고 업무도 아니고 의무도 아니다. 기여일 뿐이다. 하지만 같이 작업을 진행하려면 투명하게 해야 한다. 사정이 생겨 진행이 늦어 질수도 있고, 진행을 아예 못할 수도 있다. 결과가 만족스럽지 않을 수도 있다. 혼자 고민하지 마시고 적극적으로 도움을 요청해주셨으면 한다. 많이 활용하셨으면 한다. 그러라고 멘토가 있는 것... 이겠지.

# 링크들

- 2021 오픈 컨트리뷰션 아카데미
    - 홈 : [https://www.oss.kr/contribution_academy](https://www.oss.kr/contribution_academy)
    - 딥러닝(케라스) 실용 예제 구축 : TODO : add link
    - 딥러닝(케라스) 실용 예제 구축 기여 가이드 : TODO : add link
    - 프로젝트 소개 : [https://www.oss.kr/contribution_academy_project/show/17123dce-d1a3-4fc3-8949-f87c5bb479e5](https://www.oss.kr/contribution_academy_project/show/17123dce-d1a3-4fc3-8949-f87c5bb479e5)
    - 멘티 모집 공고 : [http://aifactory.space/keraskorea/task/detail.do?taskId=T002021](http://aifactory.space/keraskorea/task/detail.do?taskId=T002021)
    - 2020년 발대식 후기 : [https://www.oss.kr/contributhon_notice/show/52b27a85-a296-4d21-96df-3e83e90b8ff6](https://www.oss.kr/contributhon_notice/show/52b27a85-a296-4d21-96df-3e83e90b8ff6)
- 컨트리뷰션 작업 관련
    - 예제 현황 : [https://docs.google.com/spreadsheets/d/1AqPGDcMo9cr02JqK23ntSBGCk-dOTvXtR6gtNlqmA0M/edit#gid=0](https://docs.google.com/spreadsheets/d/1AqPGDcMo9cr02JqK23ntSBGCk-dOTvXtR6gtNlqmA0M/edit#gid=0)
    - 문서 작성 가이드 라인 : [https://github.com/keras-team/keras-docs-ko#번역-가이드라인](https://github.com/keras-team/keras-docs-ko#%EB%B2%88%EC%97%AD-%EA%B0%80%EC%9D%B4%EB%93%9C%EB%9D%BC%EC%9D%B8)
    - 작업 내역 문서 template : [working_history.md](https://vscode-remote+green-coyote-vk8zh7dc.ws-us13.gitpod.io.vscode-resource.gitpod.io/workspace/keras-docs-ko/examples/working_history.md)
    - 2020 KLD : 2020년 KLD(Keras Learning Day) : [http://aifactory.space/kld](http://aifactory.space/kld)
    - gitpod : 온라인 git 작업 환경 : [https://gitpod.io/](https://gitpod.io/)
    - Colab : [https://colab.research.google.com/](https://colab.research.google.com/)
- 커뮤니케이션
    - 멘토 임도형 :
    - 멘토 김태영 :
    - slack : TODO : add_link
    - 카톡방 : TODO : 필요한지 고민, 필요하면 링크 추가
- Keras Example
    - home : [https://keras.io/examples/](https://keras.io/examples/)
    - github : [https://github.com/keras-team/keras-io/tree/master/examples](https://github.com/keras-team/keras-io/tree/master/examples)

# TODO

- 발대식 TODO
    - ~~멘토~~, 멘티 소개
    - ~~컨트리뷰션 가이드 설명~~
    - ~~커뮤니케이션 방법 설명~~
    - ~~리뷰 방법 결정~~ : 방안 마련하여 투표로
    - ~~팀 운영비 사용~~ : 고민 후 결정
- ~~컨트리뷰션 가이드 초안 작성~~
- 컨트리뷰션 가이드 마무리
- 예제 선정
    - ~~구글 시트 보완~~
    - 구글 시트 리스트 업데이트
    - 신청
    - 선정
- 리뷰 방법 마련
- ~~리뷰 기준 검토~~
- 결과물 샘플 작성(임도형, 김태영)
- 라이센스 요청 메일 템플릿 작성
- 작업 방법을 녹화해서 youtube로 올리기
- 경진대회 가이드 추가
- 라이센스 관련 가이드 추가
-