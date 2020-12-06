# JAVA SWING 팁 모음

<hr>

## JSCrollPane(JTable)

### 1. 스크롤바 없애기
- JScrollPane Properties -> horizontal(vertical)ScrollBarPolicy -> NEVER, AS NEEDED 체크

- <b>스크롤 바를 없애면 기존의 `MouseWheelMoved` 이벤트가 적용이 되지않는다.</b>
  - 따라서 <b>MouseWheelMoved</b> 를 직접 구현해줘야한다.
  ```java
      private void jScrollPane2MouseWheelMoved(java.awt.event.MouseWheelEvent evt) {                                             
        int TableRowHeight = jTable1.getRowHeight();
        if (evt.getUnitsToScroll() > 0) {
            jScrollPane2.getVerticalScrollBar().setValue(jScrollPane2.getVerticalScrollBar().getValue() + TableRowHeight); // 각 행의 Height 만큼씩 Scroll이 움직인다.
            //TableRowHeight 자리에 원하는 숫자를 넣어 스크롤 속도를 조절할 수 있다.
        } else {
            jScrollPane2.getVerticalScrollBar().setValue(jScrollPane2.getVerticalScrollBar().getValue() - TableRowHeight);
        }
    }  
    ```
    
### 2. JScrollPane 안에 포함된 컴포넌트 투명하게 설정하기
- Swing 컴포넌트를 투명하기 위해선 `SetOpaque(false)` 를 사용하면 된다.
- JScrollPane 안에 포함 된 컴포넌트의 경우는 컴포넌트 자신 뿐만 아니라 JScrollPane 까지 `SetOpqaue()`로 투명도 설정을 해줘야한다.

```JAVA
        JScrollPane.setOpaque(false);
        JScrollPane.getViewPort().setOpaque(false);
```

### 3. 테이블 헤더 색상 변경
1. UI 변경 (<b>BasicTableUI</b>로 변경을 해줘야 헤더 색상 변경 가능)
 ```java
        jtable.setUI(new BasicTableUI()); // 테이블 UI 변경
        jtable.getTableHeader().setUI(new BasicTableHeaderUI()); // 테이블 헤더 UI 변경
```
2. JTabelHeader 객체 생성 후 배경 색 설정
```JAVA
        JTableHeader tbh = jtable.getTableHeader(); // 테이블 헤더 받아옴
        
        tbh.setFont(new Font("Segoe UI", Font.BOLD, 12)); // 테이블 헤더의 폰트 설정
        tbh.setOpaque(false); // Opaque(투명도) 를 false로 해줘야 색상 적용됨
        tbh.setBackground(new Color(255, 255, 255)); // 테이블 헤더의 배경색 설정
        tbh.setForeground(new Color(0, 0, 0)); // 테이블 헤더의 글자색 설정
```

### 4. JScrollPane의 위치를 최하단으로 설정하기
- JScrollPane 안에 있는 컴포넌트가 포커스를 얻었을 때 사용하면 좋다. (게시판 등)

 ```JAVA
        jScrollPane.getVerticalScrollBar().setValue(jScrollPane.getVerticalScrollBar().getMaximum());
```

<hr>

## ComboBox

### 1. ComboBox 배경 투명하게 설정
 - ComboBox Properties -> BackGroundColor -> Custom Code 선택
 ```JAVA
        ComboBox(객체 이름).setBackground(new java.awt.Color(255,255,255,0)); // 투명도 0 ~ 255
 ```
 
 <hr>
 
 ## ImageIcon
 
 ### 1. JLabel 에 이미지 넣기
 
 1. Ant 프로젝트 
 ```JAVA
          JLabel.setIcon(new ImageIcon("imagePath(이미지 경로)"));
 ```
 
 2. Maven 프로젝트
  - Maven 의 경우 이미지는 <b>src/main/resources</b> 경로에 있어야 인식을한다. 위의 경로가 아니라면 ImageIcon에서 `NullPointerException` 발생
 ```JAVA
          JLabel.setIcon(new ImageIcon(getClass().getResource("imagePath(이미지 경로)")));
 ```
 
 <hr>
 
 ## JTextField
 
 ### 1. JTextField 텍스트 초기화하기
 - TextField가 포커스를 얻기 전 기본 텍스트가 지정 되어있고, 포커스를 얻으면 텍스트가 사라짐
 - 아무것도 입력하지 않은채 포커스를 잃었을 경우 기본 텍스트로 다시 지정되고, 텍스트가 입력 된 경우에는 해당 텍스트를 유지
 
 ```java
     public void TextFieldGained(JTextField jtf, String baseStr) { //FocusGaine 이벤트
        if (jtf.getText().trim().equals(baseStr.trim())) {
            jtf.setFont(new java.awt.Font("맑은 고딕", 0, 12));
            jtf.setForeground(new Color(0, 0, 0));
            jtf.setText("");
        }
    }

    public void TextFieldLost(JTextField jtf, String baseStr) { //FocusLost 이벤트
        String text = jtf.getText();

        if (("".equals(text.trim()))) {
            jtf.setFont(new java.awt.Font("Dialog", 1, 14));
            jtf.setForeground(new Color(204, 204, 204));
            jtf.setText(baseStr);
        }
    }
```

<hr>

## JFrame

### 1. JFrame 종료하기

1. ext()
 - exit(0) 실행 중인 모든 프레임을 닫는다
 ``` JAVA
        System.exit(0);
```
    - 특정 Frame에서 또 다른 Frame을 팝업 형식으로 띄워야하는 경우가 있는데 이럴 때 exit()를 쓰면 모든 프레임이 닫혀 버린다.

2. dispose()
- 특정 프레임만 닫는다.
```JAVA
       this.dispose();
```
    - dispose()를 사용하면 특정 Frame에서 다른 Frame을 띄웠을 때 기존 프레임은 유지한 채 팝업 Frame만 닫을 수 있다,

### 2. JFrame에서 또 다른 JFrame을 호출 했을 경우 부모 Frame을 닫는 법

 1. 부모 Frame을 호출한 Frame의 생성자로 레퍼런스를 넘겨준다.
 ```JAVA
      parentFrame // 부모 프레임 레퍼런스 변수
      new childFrame(parentFrame);
      
      childFrame.java 에서
      parentFrame.dispose() 로 부모 프레임을 닫을 수 있다.
  ```
      
