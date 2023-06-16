# ml-go

## Summary

> Go를 활용한 머신 러닝에 나와 있는 머신러닝 관련 모델 구현들을 golang jupyter notebook 형식으로 작성해 본 기록을 올려 둔 레포지토리

- 공식 사이트: https://github.com/PacktPublishing/Machine-Learning-With-Go

## Projects

대부분의 코드는 공식 사이트의 코드를 클론한 것이다. `gophernotes` 또는 `GoNB` 환경에서 인터랙티브하게 구동하기 위한 일부 수정만 추가하였다.

- 04장은 기본적인 회귀분석에 대해 알아보는 프로젝트이다. `gophernotes` 사용.
- 05장은 로지스틱 회귀분석, 의사 결정 트리 등을 통해 이산 분류 문제를 해결하는 모델을 만들어보는 프로젝트이다. `gophernotes` 사용.
- 06장은 클러스터링을 하기 위해 k-means 모델을 사용한다. `gophernotes` 사용.
- 07장은 시계열 분석을 해보고 AR 모델까지만 적용해본다. `GoNB` 사용.
- 08장은 신경망을 외부 라이브러리를 사용하지 않고 matrix를 이용하여 직접 만들어본다. `GoNB` 사용.
- 01~03장은 golang으로 파일 입출력 다루기, 간단한 행렬 및 벡터 계산하기 등 warmup 에 해당하는 부분이므로 굳이 다루지 않았다.
- 08장에서 tensorflow api를 사용하는 부분은 모델을 공부하는 것이 아니라 단순히 api를 다루는 것을 배우는 부분이므로 굳이 다루지 않았다.
- 09장은 docker, pachyderm을 이용하여 머신러닝 모델을 버전 관리 및 운영하는 부분이므로 굳이 다루지 않았다.

## Etc.

로컬 환경에 설치해야 하는 의존 항목들이 많기 때문에 git clone 이후 레포지토리 디렉토리에서 직접 docker build를 하거나 docker hub에서 받은 이미지를 사용하는 것을 권장한다.

### Gophernotes

- https://github.com/gopherdata/gophernotes

- 내부적으로 [gomacro](https://github.com/cosmos72/gomacro) 패키지를 이용한다.
  - golang을 인터프리터로 사용할 수 있게 해 주는 패키지이다.
  - 유지보수가 멈춰서 go 1.13 이후에 추가된 메소드나 기능들(ex. `io.ReadAll`, generic, etc.)을 번역하지 못한다.
- gomacro에서 가지고 있는 패키지 의존성과 새로 이용하려는 3rd party package의 의존성 중에 맞지 않는 항목이 있는 경우 에러가 발생하며 코드를 실행하지 못한다. 이런 경우 gomacro는 건들 수 없기 때문에 강제로 gomacro에만 있는 패키지 의존성을 3rd party package 안에서 설치하여 상대 경로로 이용하여야 했다. 이에 대한 예시는 [chapter05 README](./chapter05/README.md)에 있다.

### GoNB

- https://github.com/janpfeifer/gonb

- 최신 버전인 v0.7.0은 2023년 5월 29일에 나왔을 정도로 계속해서 발전 중인 프로젝트이다.
- `gophernotes` 에서와 다르게 REPL(Read, Eval, Print, Loop) 방식을 사용한다. golang의 컴파일 속도가 굉장히 빠르다는 점을 이용하여 매번 새로 컴파일을 진행하지만 마치 인터프리터처럼 동작하는듯이 사용자가 체감할 수 있는 것이다.
- `gophernotes` 의 코드를 기본으로 하여 프로젝트가 시작되었으나 현재는 그 잔재가 거의 남아 있지 않다고 한다.
