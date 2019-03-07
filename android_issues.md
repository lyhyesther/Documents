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
