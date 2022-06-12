# Linux (ubuntu 20.04.4 LTS)
## pwd
Print Working Directory : 현재 어떤 디렉토리경로에 있는가를 절대경로로 표시한다
```
root@10413:~# pwd
```
+ 실행 결과
```
/root
```

---
---
## cd
Change Directory :  작업디렉토리의 위치를 바꾼다
```
root@10413:~# cd /
```
+ 실행결과 : 최상위 루트디렉토리로 이동↓
```
root@10413:/#
```
---
```
root@10413:~# cd ..
```
+ 한 단계 상위디렉토리로 이동
---
```
root@10413:~# cd
```
+ 자기 자신의 홈디렉토리로 이동
---
---
## mkdir
Make Directory : 작업 디렉토리의 하위 디렉토리 생성한다
```
root@10413:~# mkdir myfolder
```
+ 현재 디렉터리의 하위디렉토리인 myfolder가 생김
---
---
## rm
Remove : 삭제한다
```
root@10413:~/myfolder# rm hello.text
```
+ 실행결과 : myfolder 디렉토리 안에 있는 hello.text 삭제
---
```
root@10413:~# rm -r myfolder
```
+ myfolder라는 디렉토리 삭제
---
```
root@10413:~# rm -rf myfolder
```
+ myfolder라는 디렉토리 하위디렉토리까지 삭제
---
---