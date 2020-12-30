# AlertDialog 띄우기
<hr>

```JAVA
public void createDialog(final boolean typeParam){
        
        ad.setTitle("Title");
        ad.setMessage("Message");

        final EditText et = new EditText(MainActivity.this);
        ad.setView(et);

        ad.setPositiveButton("Ok", new DialogInterface.OnClickListener() { // 확인 버튼 설정
            @Override
            public void onClick(DialogInterface dialog, int which) {
                          //value에 입력한 값이 들어감
                          String value = et.getText().toString();
                        }
                    }
                dialog.dismiss();
            }
        });

        ad.setNegativeButton("Cancle", new DialogInterface.OnClickListener() { // 취소 버튼 설정
            @Override
            public void onClick(DialogInterface dialog, int which) {
                // 다이얼로그를 닫음
                dialog.dismiss();
            }
        });

        ad.show();
    }
