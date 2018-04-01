#1
  dir리스트가 보이지 않게 하기 (.htaccess)
 
    .htaccess는 사이트의 접근 제어 및 각종 설정 가능하다.
 
    1. file 내용 (문서내용)
    디렉토리명만으로 접근하는 DirectoryIndex로 지정한 파일이 없었을 때, 디렉토리 리스트가 보이는 경우가 있다. 이를 방지하기 위해 .ht를 뒤쪽에 기입한  다.
    
    2. file 생성 장소 (어디에 복사해두면되는지)
    
    .htaccess 파일이 존재하는 디렉토리로 복사한다.

#2
 * git 공동 작업을 위한 명령
 
    1. clone on fork (포크하는 방법)
    가상으로 공동작업을 위한 환경을 만들기위해 fork를 작성한다.
    
    $cd ~
    $mkdir 1 2
    $cd 1; git clone http://github.com/(git_id)/(storage_name).git
    $cd 2; git clone http://github.com/(git_id)/(storage_name).git
    
    2. 작업 후 commit하면 조장이 어떻게 합치는지(포크한것을 수정해서 커밋하면 승인하는방법)
    작업 후 commit하기
    
    changed by 1's directory
    $git add. (add명령을 이용해 새로 생성된 file을 storage area로 추가)
    $git commit -m "1's commit" (git에 commit 메세지 삽입)
    $git pull
    $git push
    
    _1로 인해 기본 storage가 수정됨_
    
    $cd ~/2/storage_name
    $vi README
    
    changed by 2's directory
    $git add.
    $git commit -m "2's commit" (git에 commit 메세지 삽입)
    $git pull
    
    _1의 수정과 2의 수정이 중복됐다는 메세지 출력, README.md에 2에서 수정한 것이 HEAD에, ======== 하단 부분에 1에서 수정한 부분을 확인할 수 있음수정을 원하는 부분을 제외하고 삭제_
    
    $git add.
    $git commit -m "merge commit"
    $git push
    
    _1의 작업 및 2의 작업병합 후 기본 storage에 저장_
