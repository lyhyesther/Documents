
# Android设备唯一性检验

IMEI
Mac 地址
ANDROID_ID
Serial Number, SN(设备序列号)
UniquePsuedoID

mac地址不可信
锤子手机，开启4G高速网络后，会重启设备，获取的mac值发生变化

# Android设备设置界面打开
1、有权查看使用情况
当应用需要查看设备上应用的使用情况的时候，可以打开该权限。
①应用需要在manifest中声明权限
 <uses-permission android:name="android.permission.PACKAGE_USAGE_STATS" />
 注意：该权限使用校验权限的方式去获取权限是否打开，总是返回的权限拒绝。当权限拒绝时，queryUsageStats返回的集合大小总是0，因此当集合大小为0的时候，权限就可能被拒绝了
②引导用户去打开权限
 startActivity(new Intent(Settings.ACTION_USAGE_ACCESS_SETTINGS));
③获取使用情况列表
 UsageStatsManager usageStatsManager = (UsageStatsManager) activity.getSystemService(Context.USAGE_STATS_SERVICE);
 long now = System.currentTimeMillis();
 long start = now - 24 * 60 * 60 * 1000L;
 List<UsageStats> usageStatsList = null;
 usageStatsList = usageStatsManager.queryUsageStats(UsageStatsManager.INTERVAL_DAILY, start, now);
