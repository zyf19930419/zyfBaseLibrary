LoadingLayout 

Usage
在主题中设置默认样式

<style name="AppTheme" parent="Theme.AppCompat.Light.DarkActionBar">
    ...
    <item name="styleLoadingLayout">@style/LoadingLayoutStyle</item>
</style>

<style name="LoadingLayoutStyle" parent="LoadingLayout.Style">
    <item name="llEmptyImage">@mipmap/empty</item>
    <item name="llErrorImage">@mipmap/error</item>
    ...
</style>
用法一：在布局中使用

<com.zhangyunfei.baselibrary.loadingview.LoadingLayout
    android:id="@+id/loading"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <TextView
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:gravity="center"
        android:text="This is Content"/>
        
</com.zhangyunfei.baselibrary.loadingview.LoadingLayout>
 
用法二：包裹并替换内容元素

@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);
    
    // ...
    
    vLoading = LoadingLayout.wrap(this); 
    vLoading.showContent(); 
    
    // ...
}
API

// 显示 content/loading/empty/error 布局
showContent()
showLoading()
showEmpty()
showError()

// 设置 loading/empty/error 布局
setLoading(int resId)
setEmpty(int resId)
setError(int resId)

// 设置空布局的图片与文本
setEmptyImage(int resId)
setEmptyText(String value)

// 设置错误布局的图片与文本，
setErrorImage(int resId)
setErrorText(String value) 

// 设置重试按钮文本
setRetryText(String value)

// 设置重试按钮的监听回调
setRetryListener(OnClickListener listener)
属性

<declare-styleable name="LoadingLayout">
    <!-- 空布局资源id -->
    <attr name="llEmptyResId" format="reference"/>
    <!-- 加载中布局资源id -->
    <attr name="llLoadingResId" format="reference"/>
    <!-- 错误布局资源id -->
    <attr name="llErrorResId" format="reference"/>

    <!-- 空布局图片 -->
    <attr name="llEmptyImage" format="reference"/>
    <!-- 空布局文本 -->
    <attr name="llEmptyText" format="string"/>

    <!-- 错误布局图片 -->
    <attr name="llErrorImage" format="reference"/>
    <!-- 错误布局文本 -->
    <attr name="llErrorText" format="string"/>
    <!-- 错误布局重试按钮文本 -->
    <attr name="llRetryText" format="string"/>

    <!-- 文本颜色 -->
    <attr name="llTextColor" format="color"/>
    <!-- 文本尺寸 -->
    <attr name="llTextSize" format="dimension"/>

    <!-- 按钮文本颜色 -->
    <attr name="llButtonTextColor" format="color"/>
    <!-- 按钮文本尺寸 -->
    <attr name="llButtonTextSize" format="dimension"/>
    <!-- 按钮背景 -->
    <attr name="llButtonBackground" format="reference"/>
</declare-styleable>
