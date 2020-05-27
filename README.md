# 쉘스크립트 공부하자!

## Project
### count-commit

이름 그대로 커밋을 카운트 한다.
다만 월별과 누적 그리고 해당 디렉토리 안에 존재하는 모든 저장소의 커밋 누적 개수 를 조회할수 있다.


#### Usage

최초 1회는 카운트 하고자 하는 저장소를 **clone** 해야 한다.
이후 `count-commit` 을 통해서 저장소들의 커밋 개수를 확인하면 된다.

현재는 2가지의 조회 옵션이 있다.

`option 1`
merge 메세지 커밋을 제외한 순수 커밋만 조회

`option *`
모든 커밋을 조회


물론 쉘 전역에서 명령어 처럼 사용 하고 싶다면 명령어를 bin에 등록해 주면 된다.

```shell
$ sudo cp count-commit /usr/local/bin/
$ count-commit
```

#### Example

```shell
$ cd test
$ tree ./
./
├── count-commit
├── Centos
└── Codex
$ ./count-commit
Please Select Operation option
[1] : Counting git commit with Merge commit
[*] : Counting git commit without Merge commit

Counting Commit without Merge Commit
========Count [Centos]=========
이미 업데이트 상태입니다.
 1월 : 0
 2월 : 0
 3월 : 0
 4월 : 1
 5월 : 0
 6월 : 0
 7월 : 0
 8월 : 0
 9월 : 0
10월 : 0
11월 : 0
12월 : 0
Total commit : [1]
================Done===============
========Count [Codex]=========
이미 업데이트 상태입니다.
 1월 : 10
 2월 : 12
 3월 : 7
 4월 : 4
 5월 : 3
 6월 : 0
 7월 : 0
 8월 : 0
 9월 : 0
10월 : 0
11월 : 0
12월 : 0
Total commit : [36]
================Done===============
Expected Commit [37/400]
```