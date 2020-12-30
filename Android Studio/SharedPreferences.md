# SharedPreferences
<hr>


- 데이터의 양이 많거나 중요한 데이터라면 **서버**나 **DB**, **파일**의 형태로 저장을 하면 되겠지만, 간단한 설정 값이나 문자열 같은 데이터들은 DB에 저장하기에는 부담스럽고 애매하다.
- 이런 경우 안드로이드에서 기본적으로 제공되는 **SharedPreferences**를 사용하여 데이터를 관리한다면 좀 더 편리하게 사용이 가능하다.
- **SharedPreferences**는 데이터를 파일로 저장 한다. **파일이 앱 폴더 내에 저장**되므로 **앱을 삭제하면 데이터도 삭제**된다.
    - 파일이 저장되는 위치
        ``` data/data/(package_name)/shared_prefs/SharedPreference```


```Java

import android.content.Context;
import android.content.SharedPreferences;
/**
 * 데이터 저장 및 로드 클래스
 */

public class PreferenceManager {

    public static final String PREFERENCES_NAME = "rebuild_preference";
    private static final String DEFAULT_VALUE_STRING = "";
    private static final boolean DEFAULT_VALUE_BOOLEAN = false;
    private static final int DEFAULT_VALUE_INT = -1;
    private static final long DEFAULT_VALUE_LONG = -1L;
    private static final float DEFAULT_VALUE_FLOAT = -1F;

    // Context는 클래스를 넣어준다. (ex. main 클래스에서 사용하면 main클래스를 넣어줌(호출하는 곳에서 this로 인자를 넘겨주면된다.))
    private static SharedPreferences getPreferences(Context context) {
        return context.getSharedPreferences(PREFERENCES_NAME, Context.MODE_PRIVATE);
    }
    
    /**
     * String 값 저장
     * @param context
     * @param key
     * @param value
     */

    public static void setString(Context context, String key, String value) {
        SharedPreferences prefs = getPreferences(context);
        SharedPreferences.Editor editor = prefs.edit();
        editor.putString(key, value);
        editor.commit();
    }

    /**
     * boolean 값 저장
     * @param context
     * @param key
     * @param value
     */

    public static void setBoolean(Context context, String key, boolean value) {
        SharedPreferences prefs = getPreferences(context);
        SharedPreferences.Editor editor = prefs.edit();
        editor.putBoolean(key, value);
        editor.commit();
    }

    /**
     * int 값 저장
     * @param context
     * @param key
     * @param value
     */

    public static void setInt(Context context, String key, int value) {
        SharedPreferences prefs = getPreferences(context);
        SharedPreferences.Editor editor = prefs.edit();
        editor.putInt(key, value);
        editor.commit();
    }

    /**
     * long 값 저장
     * @param context
     * @param key
     * @param value
     */

    public static void setLong(Context context, String key, long value) {
        SharedPreferences prefs = getPreferences(context);
        SharedPreferences.Editor editor = prefs.edit();
        editor.putLong(key, value);
        editor.commit();
    }

    /**
     * float 값 저장
     * @param context
     * @param key
     * @param value
     */

    public static void setFloat(Context context, String key, float value) {
        SharedPreferences prefs = getPreferences(context);
        SharedPreferences.Editor editor = prefs.edit();
        editor.putFloat(key, value);
        editor.commit();
    }

    /**
     * String 값 로드
     * @param context
     * @param key
     * @return
     */

    public static String getString(Context context, String key) {
        SharedPreferences prefs = getPreferences(context);
        String value = prefs.getString(key, DEFAULT_VALUE_STRING);
        return value;
    }

    /**
     * boolean 값 로드
     * @param context
     * @param key
     * @return
     */

    public static boolean getBoolean(Context context, String key) {
        SharedPreferences prefs = getPreferences(context);
        boolean value = prefs.getBoolean(key, DEFAULT_VALUE_BOOLEAN);

        return value;
    }



    /**
     * int 값 로드
     * @param context
     * @param key
     * @return
     */

    public static int getInt(Context context, String key) {
        SharedPreferences prefs = getPreferences(context);
        int value = prefs.getInt(key, DEFAULT_VALUE_INT);
        return value;
    }
    /**
     * long 값 로드
     * @param context
     * @param key
     * @return
     */

    public static long getLong(Context context, String key) {
        SharedPreferences prefs = getPreferences(context);
        long value = prefs.getLong(key, DEFAULT_VALUE_LONG);

        return value;
    }

    /**
     * float 값 로드
     * @param context
     * @param key
     * @return
     */

    public static float getFloat(Context context, String key) {
        SharedPreferences prefs = getPreferences(context);
        float value = prefs.getFloat(key, DEFAULT_VALUE_FLOAT);

        return value;
    }

    /**
     * 키 값 삭제
     * @param context
     * @param key
     */

    public static void removeKey(Context context, String key) {
        SharedPreferences prefs = getPreferences(context);
        SharedPreferences.Editor edit = prefs.edit();
        edit.remove(key);
        edit.commit();
    }

    /**
     * 모든 저장 데이터 삭제
     * @param context
     */

    public static void clear(Context context) {
        SharedPreferences prefs = getPreferences(context);
        SharedPreferences.Editor edit = prefs.edit();
        edit.clear();

        edit.commit();
    }
}
```
