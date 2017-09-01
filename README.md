# EditText
Android EditText设置键盘搜索和错误验证<br>

##### 搜索功能只需xml设置即可<br>
----
```xml
<EditText
     android:id="@+id/name_input"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:imeOptions="actionSearch"
    android:singleLine="true" />
```
android:imeOptions设置成actionSearch为搜索功能，设置成actionDone确定功能，
一定要用android:singleLine="true"，不能用android:maxLines="1"，否则无效<br>
##### 验证功能java代码<br>
----
```java

EditText nameInput;

private void checkInput() {
        nameInput.setError(null);
        String name = objectNameInput.getText().toString();

        boolean cancel = false;
        
        View focusView = null;
        
        if (TextUtils.isEmpty(name)) {
            nameInput.setError("姓名不能为空");
            focusView = nameInput;
            cancel = true;
        } 

        if (cancel) {
            focusView.requestFocus();
        } else {
            //验证成功
        }
    }
```
