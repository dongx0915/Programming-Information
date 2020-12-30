# CustomThread
<hr>

- 안드로이드 스튜디오에서는 **Original Thread**만 **View**를 변경할 수 있다.
- 따라서 **Thread**에서 **View**를 수정하려면 **CustomThread**를 구현해줘야한다.



- **CustomThread** 구현

```Java
class CustomThread{
        private boolean runFlag;
        private TimerTask second;
        private final Handler handler = new Handler();

        public CustomThread() {
            this.runFlag = true;
        }

        public void setRunFlag(boolean runFlag) {
            this.runFlag = runFlag;
        }

        public void testStart() {
            second = new TimerTask() {
                @Override
                public void run() {
                    if(!runFlag) return;
                    Update();
                }
            };
            Timer timer = new Timer();
            timer.schedule(second, 0, 1000);
        }

        protected void Update() {
            Runnable updater = new Runnable() {
                public void run() {
                    if(!runFlag) return;
                    // Contents
                }
            };
            handler.post(updater);
        }
    }
```

- **CustomThread** 호출
  - 원하는 곳에서 위에서 구현한 testStart()를 호출해주면 된다.

```Java
      ct = new CustomThread();
      ct.testStart();
```

- **CustomThread** 종료
  - 종료
```Java
     // CustomThread의 RunFlag 변수를 false로 설정
      ct.setRunFlag(false);
```

- **CustomThread** 재시작
  - 재시작
```Java
      // 기존에 실행되고 있던 CustomThread를 종료시킴
      ct.setRunFlag(false);
      
      // 스레드 종료 후 다시 CustomThread 객체 생성
      ct = new CustomThread();
      ct.testStart();
```
