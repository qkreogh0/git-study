# git
!! git bash를 사용한다

!! https://git-scm.com/docs 참조
1. git 환경 설정하기 : git config 명령을 사용

    - git config --global user.name "이름"

    - git config --global user.email "메일 주소"

      ``` 
      $ git config --global user.name "daeho"
      $ git config --global user.email "eogh7204@gmail.com"
      ```
       !! github 계정이 여러 개라면 --global 옵션 사용을 하지 않고 각 계정마다 git 환경 설정을 해야 한다. 
--------------------------------------------
## !! 미리 알아두면 좋은 리눅스 명령       
- ~ : 홈 디렉터리를 의미한다
- . : 현재 디렉터리를 의미한다
- .. : 부모 디렉터리를 의미한다

- pwd : "print working directory"의 줄임말로 현재 위치의 경로를 보여준다
  ```
  $ pwd
  /c/Users/eogh7  
  ```    
- ls : "list"의 줄임말로 현재 디렉터리에 있는 파일, 디렉터리를 보여준다 
  - ls 와 같이 쓰이는 옵션
    ```
    $ ls -a
    ```

    - a : ls 와 같이 쓰여 숨긴 파일이나 디렉터리도 함께 표시한다

    - l : ls 와 같이 쓰여 파일, 디렉터리의 상세 정보를 함께 표시한다
    - r : 파일의 정렬 순서를 거꾸로 표시한다
    - t : 파일 작성 시간순으로 표시한다 (내림차순)
      
      **!! 위의 옵션들은 아래와 같이 동시에 쓰일 수 있다**
      ```
      $ ls -la
      ```    
- cd : "change directory" 의 줄임말로 현재 디렉터리의 경로를 바꿔준다 
  ```
  $ cd /c/Users/Documents
  ```      
- mkdir : "make directory" 의 줄임말로 현재 디렉터리에 새로운 디렉터리를 추가한다
  ```
  $ mkdir test
  ```
- rm : "remove" 의 줄임말로 현재 디렉터리에 있는 특정 디렉터리를 삭제한다
  ```
  $ rm -r test
  ```  
    **!! 이때 -r 옵션과 같이 쓰면 지우려는 디렉터리의 하위 디렉터리와 파일까지 모두 삭제한다**
- clear : 터미널에 있는 명령들을 모두 지운다
  ```
  $ clear
  ```
- exit : 터미널 창을 닫는다
  ```
  $ exit
  ```    
- vim : 리눅스의 기본 텍스트 편집기를 사용하게 하는 명령어
  ```
  $ vim test.txt
  ```  
  <small>위와 같이 명령을 할 경우 현재 디렉터리에 test.txt 파일이 있는지 확인하고 있다면 파일을 열고 없다면 새로운 파일을 만든다
  <br><br>
  기본은 ex 모드로 저장, 종료만 가능하고 텍스트 입력, 수정은 불가능하다
  I 또는 A 를 입력하면 입력모드로 바뀌어 텍스트 입력, 수정이 가능해지고, 다시 ex 모드로 돌아오기 위해선 esc 를 누른다
    - ex 모드에서 사용할 수 있는 옵션
      - : w 또는 : write - 편집하던 문서를 저장한다

      - : q 또는 : quit - 편집기를 종료한다
      - : wq - 편집하던 문서를 저장하고 종료한다 (뒤에 파일명을 지정해서 지정한 파일 이름으로 저장할 수 있다)</small>
- touch : 0바이트의 파일을 생성하는 명령어
  ```
  $ git touch file1
  ```      
  <small>!! file1 파일을 생성한다 </small>
- cat : "concatenate" 의 줄임말로 텍스트 문서의 내용을 간단히 확인할 수 있다
  ```
  $ cat test.txt
  문 서 내 용 입 니 다
  ```
  ```
  $ cat test.txt test1.txt > test2.txt
  ```
  위와 같이 쓰면 test.txt, test1.txt 파일이 합쳐진 test2.txt 파일이 현재 디렉터리에 생긴다
  ```
  $ cat test.txt >> test1.txt
  ``` 
  위와 같이 쓰면 test.txt 의 내용을 test1.txt 내용 끝에 연결한다 
------------------------------------
  2. git 구성
  - 작업 트리 : 우리 눈에 보이는 디렉터리로 파일 수정, 저장 등의 작업을 하는 디렉터리다

  - 스테이지 : 버전으로 만들 파일이 대기하는 곳으로 작업 트리에서 작성한 파일 중 저장소에 올라갈 파일들이 대기하는 곳이다

  - 저장소 : 스테이지의 파일들이 버전으로 올라와 저장되는 곳이다

  3. git 관련 명령어

  - git init : init 은 "initialize" 의 줄임말로 현재 디렉터리에 git을 사용할 수 있도록 저장소를 만들어 준다

    ```
    $ git init
    ```
    ```
    $ git init newDirectory 
    ```
    <small>!! 위와 같이 newDirectory 디렉터리를 새로 만들면서 저장소를 한번에 만들 수 있다 </small>
    
    **!! 이때 git 저장소는 감춰져 있으므로 보기 탭에서 숨긴 항목을 체크해야 볼 수 있다**
  - git status : git 의 상태 메세지를 보여주는 명령어
    ```
    $ git status
    ```
  - git add : 작업 트리의 파일을 스테이지로 스테이징할 수 있게 해주는 명령어
    ```
    $ git add test.txt
    ```
  - git commit : 스테이지에 대기 중인 파일을 저장소로 커밋하게 하는 명령어
    ```
    $ git commit -m "message"
    ```  
    <small> !! 위와 같이 -m 옵션과 같이 쓰여 커밋과 함께 저장할 메세지를 적는다<br>
    !! --amend 옵션과 같이 쓰여 가장 최근 커밋 메세지를 수정할 수 있다
    </small>

  - git log : 저장소에 저장된 버전을 확인할 때 사용하는 명령어로 버전마다 해시태그, 만든 사람, 만든 시각, 커밋 메세지를 보여준다
    ```
    $ git log
    ```  
    <small> --stat 옵션과 같이 사용해 커밋에 관련된 파일까지 살펴볼 수 있다</small>
  - git commit -am : 한번 커밋이 된 파일을 작업 트리에서 다시 수정할 경우 스테이징 과정없이 바로 커밋시키는 명령어로 뒤에 커밋과 함께 저장할 메세지를 적는다
    ```
    $ git commit -am "message1"
    ```
  - git diff : 작업 트리, 스테이지의 파일을 저장소에 있는 최근 버전과 비교해서 어떤 부분이 다른지 알려주는 명령어
    ```
    $ git diff
    ```   
  - git restore : 작업 트리에서 수정한 파일을 저장소에 있는 가장 최신 버전 파일로 되돌릴 때 사용하는 명령어
    ```
    $ git restore test.txt
    ``` 
    ```
    $ git restore --staged test.txt
    ```    
    <small> 스테이지에 있는 test.txt 파일을 다시 내린다</small>
    ```
    $ git restore --staged 
    ```    
    <small> 스테이지에 있는 모든 파일을 다시 내린다</small>
  - git reset : 커밋을 삭제시키는 명령어
    ```
    $ git reset HEAD^
    ```
    <small>가장 최신의 커밋을 삭제하는 명령어</small>
    ```
    $ git reset --soft HEAD^
    ```
    <small>가장 최신의 커밋을 삭제하고 스테이징 상태로 내리는 명령어</small>
    ```
    $ git reset --hard f801dafb6b5eb3d985f82e36d78e56736a126fbb
    ```
    <small>버전이 갖고 있는 해시태그를 써서, 그 버전 이후의 커밋은 모두 삭제시키고 가장 최신 버전이 되는 명령어</small>
  - git revert : 특정 커밋을 삭제하지 않고 취소만 시켜 그 이력을 남겨 둘 때 사용하는 명령어
    ```
    $ git revert f801dafb6b5eb3d985f82e36d78e56736a126fbb
    ```
    <small>커밋을 취소하면서 남겨 둘 내용을 입력할 수도 있다</small>
4. 브랜치

    <img src=https://techblog.woowahan.com/wp-content/uploads/img/2017-10-30/github-flow_graph_for_no_rebase.png>
  - 커밋을 가리키는 포인터로 새 브랜치를 만드는 것을 분기한다고 한다

    - git branch : 만들어져 있는 브랜치를 확인하거나 브랜치를 새로 만드는 명령어

        <small>!! 브랜치를 확인</small> 
      ``` 
      $ git branch  
      ``` 
      <small>!! apple 브랜치 생성</small> 
      ``` 
      $ git branch apple  
      ```   
    - git log --oneline : 한 줄에 한 커밋씩 보여주는 명령어 
    - git log --branches : 브랜치마다 최신 커밋을 한눈에 보여주는 명령어
    - git log --all : 각 브랜치의 최신 커밋만이 아닌 모든 커밋을 보여주는 명령어
      <small>!! 아래와 같이 쓸 수도 있다</small>  
      ``` 
      $ git log --oneline --branches  
      ``` 
      <small>!! 브랜치와 커밋의 관계를 그래프로 보여준다</small>  
      ``` 
      $ git log --oneline --branches --graph  
      ``` 

    - git switch : 브랜치를 전환시키는 명령어 

      <small>!! apple 브랜치로 전환</small> 
      ``` 
      $ git switch apple  
      ``` 
    - git log branch1..branch2 : branch1 에는 없고 branch2 에만 있는 커밋을 보여주는 명령어
    
      <small>!! main 브랜치에는 없고 apple 브랜치에만 있는 커밋을   보여준다</small>
      ``` 
      $ git log main..apple 
      ``` 
  - 원하는 작업을 마친후에 문제가 없을 시에 main 브랜치에 병합한다
    - git merge : HEAD 가 가리키고 있는 브랜치에 새로운 브랜치를 병합시키는 명령어
    ```
    $ git merge branch2 
    ```
    <small>!! HEAD 가 가리키는 브랜치가 branch1 일 때, branch2 브랜치를 가져와 branch1 에 병합시킨다 <br>
      1. branch2 브랜치가 새로운 파일을 만든 경우, 병합 후에 branch1 브랜치에 branch2 브랜치에서 만든 파일이 새로 생긴다
      1. branch1 브랜치의 파일의 다른 부분을 수정을 했을 경우, 자동으로 내용을 합쳐준다
      2. branch1 브랜치에서 수정한 부분을 branch2 브랜치에서 수정했고 branch1 브랜치로 병합한 경우, 병합한 이후 그 부분을 적절히 수정해주고 다시 커밋한다</small>
    - git branch -d : 병합시켜서 더 이상 사용하지 않는 브랜치를 삭제시키는 명령어
      ```
      $ git branch -d branch1
      ```  
      <small>!! 병합된 branch1 브랜치를 삭제시킨다 <br> !! 이때, branch1 브랜치를 다시 만들면 삭제된 branch1 브랜치가 그대로 복구된다</small>

      ```
      $ git branch -D branch1
      ```
      <small>!! 위와 같이 -D 옵션을 쓰면 병합하지 않은 브랜치를 삭제시키려고 해도 오류 메세지가 나타나지 않고 강제로 삭제시킬 수 있다</small>
    - git cherry-pick : 병합을 시킬 때, 모든 파일을 병합시키는 것이 아닌, 특정 버전의 변경 내용만 합치려고 할 때 사용하는 병합 방식
      ```
      $ git cherry-pick 4eabf0d
      ```
      <small>!! 여기서 4eabf0d는 특정 버전의 해시코드</small>
  ------------------------------------
  ## github : git 을 이용할 수 있는 원격 저장소
  
  1. 지역 저장소를 원격 저장소에 연결하기

      <small>!! 원격 저장소 주소 : https://github.com/아이디/저장소명</small> 
      1. git remote add origin : 원격 저장소에 origin 을 추가하는 명령어
            <br><br>      
          ```
          $ git remote add origin https://github.com/qkreogh0/test-1.git
          ```       
          <small>!! 여기서 origin 은 뒤에 적힌 원격 저장소를 가리킨다</small>          

      2. git remote -v : 원격 저장소에 제대로 연결됐는지 확인하는 명령어
  2. 지역 저장소와 원격 저장소 동기화하기
      1. git push -u origin main : 지역 저장소의 브랜치를 origin(원격저장소)의 main 브랜치로 보내라는(push) 명령으로 이후에는 -u 옵션이나 main 브랜치 이름 없이 보낼 수 있다
          ```
          $ git push -u origin main
          ```
          <small>!! 처음에 푸시 할 때는 위와 같이 하고, 그 이후부터는 아래와 같이 한다 </small>

          ```
          $ git push
          ```
      2. git pull origin main : origin(원격저장소)을 지역 저장소의 main 브랜치로 가져오는(pull) 명령어로 이후에는 origin main 을 붙히지 않고 가져올 수 있다
          ```
          $ git pull origin main
          ```
          <small>!! 처음에 풀 할 때는 위와 같이 하고, 그 이후부터는 아래와 같이 한다 </small>

          ```
          $ git pull
          ```
  3. 원격 저장소와의 연결 끊기

  - git remote remove : 현재 지역 저장소와 연결되어 있는 원격 저장소와의 연결을 끊는 명령어

    <small>!! origin 저장소와의 연결을 끊는다</small>
    ```
    $ git remote remove origin
    ```        
-------------------------
### !! github에 SSH 원격 접속하기
- SSH : "secure shell" 의 줄임말로 private key와 public key를 한 쌍으로 묶어 컴퓨터를 인증하는 방식이다 (기기를 한번 등록해 놓으면 빈번하게 로그인을 할 필요가 없다)

  1. SSH 키 생성하기<br>
      ```
      $ ssh-keygen
      ```
      <small>!! 위의 명령어를 입력하면 id_rsa, id_rsa.pub 파일이 만들어지는데 id_rsa 는 private key로 숨겨져 있고, id_rsa.pub 는 public key 이다</small>
  2. 생성된 SSH private key 복사하기
      ```
      $ clip < 파일경로/id_rsa.pub
      ```    
      <small>!! clip 은 < 이후의 내용을 복사하는 리눅스 명령어</small>
  3. 이후는 Https 방식과 같다    

