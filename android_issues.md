## Android Font Issue
1. Prevent system font-size changing effects to android application

       public void adjustFontScale(Configuration configuration) {
              if (configuration.fontScale > 1.00) {
                  configuration.fontScale = (float) 1.00;
                  DisplayMetrics metrics = getResources().getDisplayMetrics();
                  WindowManager wm = (WindowManager) getSystemService(WINDOW_SERVICE);
                  wm.getDefaultDisplay().getMetrics(metrics);
                  metrics.scaledDensity = configuration.fontScale * metrics.density;
                  getBaseContext().getResources().updateConfiguration(configuration, metrics);
              }
          }
    
  And called it right after my super.onCreate() like:
  
         @Override
           protected void onCreate(@Nullable Bundle savedInstanceState) {
               super.onCreate(savedInstanceState);
               adjustFontScale(getResources().getConfiguration());
           }
 
## Android API Level Issue
1、Android 5.1 不支持drawable 中的item的gravity 属性的right|top bottom|left ...写法 ，在vivo Android 5.1 上测试；grivaty在Android 6.0及以上支持。
 the gravity (and size) property for LayerDrawable  added in API level 23.
 
 解决方案：
 创建不同的drawable-23 ,然后放置不同的drawable.
 
 ## Android Task Stack
1、 Android 任务栈导致的应用退至后台启动的问题
1）点击home键，不能回到之前使用的页面，会重新启动应用
主页面之前的launchMode不能设置为android:launchMode="singleTask"，只能设置为标准模式android:launchMode="standard"
遇到该类问题，需要认真梳理应用的任务栈

