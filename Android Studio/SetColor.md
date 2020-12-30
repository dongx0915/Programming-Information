# 안드로이드 스튜디오 색상 설정
<hr>

- **res/values/colors.xml** 에 색상 정보를 추가해준다.
```xml
  <?xml version="1.0" encoding="utf-8"?>
  <resources>
      <color name="colorPrimary">#6200EE</color>
      <color name="colorPrimaryDark">#3700B3</color>
      <color name="colorAccent">#03DAC5</color>
      <color name="colorGray">#252525</color>
      <color name="colorWhite">#FFFFFF</color>
      <color name="colorBlack">#000000</color>
  </resources>
```

- 사용 예시

```xml
<TextView
            android:id="@+id/textview"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"

            android:textColor="@color/colorWhite" <--
            android:textSize="20dp"
  />
```
