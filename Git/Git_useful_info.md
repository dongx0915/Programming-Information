# Git Tips

### Push해도 Repository에 변화가 없을 때
  > <b>\- Error message</b>
  > ```
  > Everything up-to-date
  > Branch 'master' set up to track remote branch 'master' from 'origin'.
  > ```
 <b>-> 이전 명령의 git add가 손상 된 경우이다.</b>
 
 > Solution : 
 > ``` 
 > git init
 > git add .
 > git commit -m "Fix Bad Repository"
 > git push
 > ```
 

 <br><br>
 <hr>
 
 
Contents            | Link
--------------------|--------
push가 안될 때 | [Blog](https://blog.shovelman.dev/924)
Git stats | [GitHub](https://github.com/anuraghazra/github-readme-stats)
Git Subtree | [GitHub](https://iseongho.github.io/posts/git-subtree/)
Git 하위 디렉토리, 폴더만 Clone하기 | [GitHub](https://www.lesstif.com/gitbook/git-clone-20776761.html)
