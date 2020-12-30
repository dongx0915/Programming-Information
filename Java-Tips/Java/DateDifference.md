# 자바 날짜 차이 계산하기
<hr>

```Java
    public void getDateDiff(Calendar blockTime, TextView diffDate, TextView diffTime){
        Calendar currentTime = Calendar.getInstance();

        long diff = currentTime.getTimeInMillis() - blockTime.getTimeInMillis();

        long days = (long)(Math.floor(diff / (1000 * 60 * 60 * 24)));
        long hours = (long)(Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60)));
        long minutes = (long)(Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60)));
        long seconds = (long)(Math.floor((diff % (1000 * 60)) / 1000));

        diffDate.setText(days +"일");
        diffTime.setText(String.format("%02d : %02d : %02d", hours, minutes, seconds));
        //%02d를 사용하면 2 자릿수로 맞추고 앞의 빈 자리는 0으로 채운다
    }


    public String getDate(Calendar date){
        SimpleDateFormat sdf = new SimpleDateFormat("yy.MM.dd HH:mm");
        return sdf.format(date.getTime());
    }
```
