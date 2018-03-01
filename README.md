# StayBarExample
Android沉浸式状态栏实现
## 一 改变状态栏颜色
````
private void setStatusColor() {
        if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.KITKAT) {
            getWindow().addFlags(WindowManager.LayoutParams.FLAG_TRANSLUCENT_STATUS);
            SystemBarTintManager tintManager = new SystemBarTintManager(this);
            tintManager.setStatusBarTintColor(getResources().getColor(R.color.colorGreen));
            tintManager.setStatusBarTintEnabled(true);
        }
    }
````
![](https://github.com/kuangxiaoguo0123/ATStayBar/blob/master/screenshots/Screenshot_2016-10-31-10-03-38.png)
## 二 最外层布局背景图片充满状态栏
````
public void setOuterLayoutFullScreen() {
        if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.KITKAT) {
            getWindow().addFlags(WindowManager.LayoutParams.FLAG_TRANSLUCENT_STATUS);
            ViewGroup rootView = (ViewGroup) ((ViewGroup) findViewById(android.R.id.content)).getChildAt(0);
            rootView.setFitsSystemWindows(true);
            rootView.setClipToPadding(true);
        }
    }
````
![](https://github.com/kuangxiaoguo0123/ATStayBar/blob/master/screenshots/Screenshot_2016-10-31-10-33-44.png)
## 三 里层布局充满状态栏
````
private void setInnerLayoutFullScreen() {
        getWindow().addFlags(WindowManager.LayoutParams.FLAG_TRANSLUCENT_STATUS);
        getWindow().getDecorView().setSystemUiVisibility(View.SYSTEM_UI_FLAG_LAYOUT_FULLSCREEN);
}
````
![](https://github.com/kuangxiaoguo0123/ATStayBar/blob/master/screenshots/Screenshot_2016-10-31-11-04-51.png)
