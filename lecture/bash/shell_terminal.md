# Shell Basic(command line interface)

[TOC]

---

### 쉘 (Shell)

> shell을 쉽게 표현하면 도스의 command.com이 하는 역할처럼 login 이후부터 사용자가 입력하는 명령어를 기계어로 변역하여 커널에 전달하는 역할을 하는 명령해석기를 말한다. 기본적으로는 bash 쉘이 사용되며 터미널 환경설정에서 다른 shell을 지정할 수도 있습니다.  

### bash
>   Bourne again shell은 최초로 개발된 쉘인 Bourne shell의 변종이라 할 수 있다. 가장 많이 사용되는 쉘이며, POSIX 호환이며 Borune shell과 호환되는 쉘로서 GNU 프로젝트에 의해 만들어지고 배포되고 있다. 명령행 편집 기능을 제공합니다.

> 참고_ 사용하는 시스템에서 사용 가능한 shell의 종류를 알아보려면 /etc/shells라는 파일을 열어보면 됩니다.

> [출처 보러가기](http://serapims.tistory.com/entry/OSX-%ED%84%B0%EB%AF%B8%EB%84%90-%EB%AA%85%EB%A0%B9%EC%96%B4)


#### mac terminal 기본적인 명령어들..
터미널 명령어 맨 앞의 $는 command line임을 알려주는 표시입니다.(별도로 작성하지 않습니다)

--
##### `$ whoami` 컴퓨터(사용자)이름 확인

##### `$ pwd` 현재 디렉토리 확인
현재 위치하고 있는 경로가 어디인지 확인할 수 있습니다.

##### `$ ls` list /현재 디렉토리에 있는 파일 및 폴더의 목록 확인
현재 위치한 경로에 어떤 파일이 있는지 확인할 수 있습니다.
* $ ls  -a : 숨겨둔 파일도 모두 표시합니다.(사이띄어쓰기)
* $ ls  -l : 리스트 형식으로 표시합니다.(사이띄어쓰기)

##### `$ cd` change directory /디렉토리 변경
- `$ cd ~`을 입력하면 자신의 홈 디렉토리로 이동하도록 되어 있습니다.
- `$ cd ..`을 입력하면 상위 디렉토리로 이동 합니다.
- `$ cd /`을 입력하면 하위나 상위 디렉토리가 아니라 최상위 디렉토리로 이동합니다.
```shell
$ cd /test_file   //- 'test' directory로 이동합니다.
```
경로상에서 `.`의 표기는 현재위치, `..`는 현재 경로에서 상위폴더, `/`의 표기는 최상단을 의미, `x/` 의(x는 폴더명)표기는  x폴더 라는 뜻을 의미 합니다.

---

##### `$ mkdir` make directory /새로운 디렉토리 생성

 만들고자하는 디렉토리의 상위 디렉토리가 없는 경우 상위 디렉토리까지 같이 만듭니다. 

```shell
$ mkdir test		  //- 'test' directory가 생성됩니다.
$ mkdir test test/box test/box/sample	//- 'test' directory 내부에 'box' directory를 생성하고 내부에 'sample' directory 생성하는 명령어로 순서대로 처리해야합니다.
$ mkdir test/box/sample -p	//- 'test' directory 내부에 'box' directory를 생성하고 내부에 'sample' directory 생성하는 기능을 중간과정 없이 생성시킵니다.
```
##### `$ touch` 비어있는 파일 생성
```shell
$ touch test_file 	//- 'test_file'파일이 생성됩니다.
```
##### `$ mv` move /파일 및 디렉토리 이동

```shell
$ mv test_file /a	//- 'test_file'을 /a로 이동시킵니다.
```
##### `$ cp` copy /파일 및 디렉토리 복사
```shell
$ cp test_file /a	//-	'test_file'을 /a로 복사합니다.
```
##### `$ rm` remove /파일 및 디렉토리 삭제
지운 파일은 복구가 불가능합니다. 연습용이 아니라면 신중히 사용하세요.

- `$ rm -r`을 입력하면 하위 디렉토리들도 삭제됩니다. (rm  뒤에오는 -r 의 경우는 옵션의 기능을 표기해 놓은 것 입니다)
- 옵션 
  -f 디렉토리 안의 파일을 삭제할 때 사용자에게 확인을 요구하지 않음 
  -r 인수 list 에서 지정한 디렉토리 혹은 그 아래의 subdirectory를 삭제 
  -i whrite permission 이 없는 파일의 삭제를 위해 대화식으로 확인 
  -p 디렉토리 dir-name과 비어있는 부모 디렉토리를 사용자가 제거할 수 있으며, 전체 경로명이 삭제 되거나 어떤 이유로 인해 경로명의 일부가 남은것과 무관하게 표준출력에 메세지가 출력됨 
  -s -p 선택항목 지정시 표준오류에 출력되는 메시지를 삭제 

```shell
$ rm test			// - 'test' directory를 삭제합니다.
$ rm test.txt		// - 'test.tst' file을 삭제합니다.
$ rm -rf test		// - 'test' directory 하위내용('test'포함)을 모두 삭제합니다.
```
##### 복합처리(&&)

두가지 이상의 기능을 복합처리하려면 명령사이에 `&&`기호를 붙이면 됩니다.

```shell
$ mkdir test && touch test/sample.txt	// - 'test' directory를 생성하고, 'test' directory내부에 'sample.txt' file을 생성합니다.
```



---



##### `$ clear` 화면 지우기 (터미널 윈도우에 복잡하게 스크롤된 내용을 모두 지울 수 있다.)
##### `$ 방향키 ↑` 이전에 입력했던 명령어(반복가능)

##### `$ 방향키 ↓` 다음에 입력했던 명령어

##### `$ !!` 이전에 사용한 명령어 다시 실행

##### `$ history` 히스토리 보기

##### `$!번호` 히스토리 번호 다시 실행

##### `$ exit` shell 종료하기

##### shell에서 탐색창 열기(각 os 마다 다릅니다.)

```shell
$ open .	// - mac
$ nautilus . 	// - linux
$ start . 	// - window
```

---

`$ echo`

`$ cat`



---

