# git lecture

<https://codeonweb.com/dashboard/> 
- 설치전 사용법이해하기 -
1. 접속(회원가입)
2. 왼쪽상단 실습클릭
3. 언어선택(git)-> 기다리면 터미널이 실행됨
4. git 입력후 엔터

> vim f1.txt -> f1.txt 생성해서 vim 으로 실행

## vim
1. i  => insert : 코드를 작성하도록 들어가는기능
2. esc => exit : 코드작성상태에서 나가기(vim을 나간것은 아니다.)
3. 나간상태에서 :wq  => :w 작성파일 저장하기,  :q vim 나가기

> cat f1.txt  -> f1.txt 파일 내용 확인하기

## git
1.  git init 
2.  git status
3.  git add 파일이름
4.  git config --global user.name 사용자이름    => 파일작성자 이름(한번만작성)
5.  git config --global user.email 메일@메일주소  => 작성자 메일등록(한번만 작성)
 6.  git commit                			=> vim이 실행됨  -> 상태정보를 알려줌
  7.  git log                   		=> 기록 확인 (나가려면 q만 계속 누르면 됨)
   8.  git branch                	=> git이 가지고 있는 branch를 확인
6.  git branch branch이름   
 10. git checkout 생성branch이름  		=> 생성branch로 이동
     11. git log -p               		=> 각각의 커밋의 소스들의 차이점을 확인하는 기능
7.  git diff commit(고유주소)..commit(고유주소)   => 선택되어진 커밋의 상태의 해당파일간의 내용 비교
    13. git tag  										=> 버전 확인
        14. git tag v1.1 							=> 버전 v1.1 
            15. git show 버전  						=> git 버전별 내용확인
8.  git remote add origin git주소   => 레파지토리생성
9.  git push -u origin branch이름  => git push 처리(아이디/ 비밀번호 물어보면 작성)

