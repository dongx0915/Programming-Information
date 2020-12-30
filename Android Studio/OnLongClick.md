# OnLongClick 이벤트

- View를 일정 시간 이상 누르면 발동되는 이벤트
- 일반적인 **Click** 이벤트가 ***SetOnClickListner()*** 메소드를 통해 리스너를 설정하였듯이 **Long Click** 이벤트는 ***SetOnLongClickListner()*** 메소드로 설정한다.
- **LongClick**은 **Click** 과 다르게 **onLongClick**이 **boolean**을 리턴한다. 이벤트 처리를 완료했을 경우 **True**

```JAVA
        ViewName.setOnLongClickListener(new View.OnLongClickListener() {
            @Override
            public boolean onLongClick(View v) {
                // Contents
                return true;
            }
        });
   ```
   
   
