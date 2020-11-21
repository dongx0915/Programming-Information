# Git
<hr>
<br>

### Git Login

> <pre><code>- git config --global user.email "useremail@example.com"
> - git config --global user.name "username"
> </pre></code>

<hr>

### Git Clone

> ```
> - cmd -> Clone 받을 폴더로 이동      (change Directory)
> - git clone repository URL          
> ```

<hr>

### Git status

> ```
> - git status
> ```

<hr>

### Git add
 - **Staging Area**에 파일을 올리는 작업
 
 >```
 > - git add FileName.*       (특정 파일만 add)
 > - git add .                (모든 파일을 add)
 >```
 
### Git reset
 - 특정 파일을 **Staging Area**에서 제거
 
> ```
> - git reset FileName.*
> ```
 
<hr>

### Git commit

>```
> - git commit -m "message"
>```

### Git push
* **commit** 후 **push**까지 해주어야 **github**에 반영됨
>```
> - git push
>```

<hr>

### Git checkout 
* 최근 수정 내역을 원상복귀

>```
> - git checkout -- FileName.*
>```
