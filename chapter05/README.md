# Chapter 05

## Todos

- [x] 로지스틱 함수
- [x] 데이터 프로파일링
- [x] 로지스틱 회귀분석
- [x] k-최근접 이웃 모델
- [x] 의사결정 트리와 랜덤 포레스트
- [x] 나이브 베이즈

## Notes

### `github.com/sjwhitworth/golearn` 패키지 사용하기

- `github.com/gopherdata/gophernotes@v0.7.5` 와 `github.com/sjwhitworth/golearn@v0.0.0-20221228163002-74ae077eafb2` 는 자동 호환 X
    - "plugin was built with a different version of package" 에러 발생
- `golearn` 레포를 직접 로컬에 받아 의존성을 강제 업데이트
    - `gomacro` 의 `go.sum` 파일을 보고 버전에 맞춰 `go get` 으로 `golearn` 패키지에 모듈 추가

```
$ git clone https://github.com/sjwhitworth/golearn
$ cd golearn
$ go get golang.org/x/sync@v0.0.0-20210220032951-036812b2e83c
$ go get github.com/mattn/go-runewidth@v0.0.13
```

- 이후 jupyter notebook 에서는 상대 경로로 사용
