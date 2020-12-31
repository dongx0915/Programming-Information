# Java 특수문자로 Split하기

<hr>

- **String**을 **Split**할 때 특수문자로 **Split**하는 경우 제대로 안되는 경우가있다.
- **점(.), 물음표(?), 별(*), 더하기(+), 괄호( '(' , ')' ), 대괄호( '[' , ']' ), 중괄호( '{' , '}' )** 등이 해당된다.
- 위와 같은 경우 Escape 처리를 해주면 된다.

- 날짜 **yy.MM.dd HH:mm** 형식의 **String**을 **Split**하는 예제
```Java

    public Calendar parseDateToCalendar(String date){
        String[] dateInfo = date.split("\\.|\\:| ");
        Calendar cal = Calendar.getInstance();
        
        int year = Integer.parseInt("20" + dateInfo[0]);
        int month = Integer.parseInt(dateInfo[1]) - 1;
        int day = Integer.parseInt(dateInfo[2]);
        int hour = Integer.parseInt(dateInfo[3]);
        int minute = Integer.parseInt(dateInfo[4]);

        cal.set(year, month, day, hour, minute, 0);

        return cal;
    }
```

- 입력
```Java
  20.12.25 17:35
```

- 출력
```Java
20
12
25
17
35
```
