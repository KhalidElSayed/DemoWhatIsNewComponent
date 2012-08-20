package com.michael.component.whatisnew;

import android.app.Activity;
import android.content.Context;
import android.content.SharedPreferences;

/**
 * This class is used for :
 * judge whether the application is first been used.-->isFirstUse(Context context)
 * And save the data if users has opened the application.-->saveFirstUseFlag(Context context)
 * 
 * example:when user open the application first time ,the method isFirstUse(Context context)will return true.
 * after user opened the application,the method saveFirstUseFlag(Context context) should be called
 * so that when user opened the application next time ,the method isFirstUse(Context context)will return false.
 * 
 * see MainActivity.java to know how to use these methods.
 * 
 * 
 * 
 * 这个类用来判断应用程序是否是第一次使用-->isFirstUse(Context context)
 * 如果用户打开过了这个程序，将标记保存-->saveFirstUseFlag(Context context)
 * 
 * 例如：当用户第一次打开应用程序的时候，isFirstUse(Context context)方法返回的是true.
 * 之后你可以调用saveFirstUseFlag(Context context)方法。这样下次用户再打开程序员的时候
 * isFirstUse(Context context)方法返回的是false.
 * 
 * 具体使用，参见MainActivity.java 
 * 
 * @author Michael 叶坤
 * @since 2012-08-07
 * */
public class WhatIsNewUtils 
{

	private static String WHAT_IS_NEW_PRE_NAME = "what_is_new_pre_name";
	
	private static String FIRST_USE_FLAG = "first_use_flag";
	 /**
	  * judge whether the first time to use this application
	  * 
      * 判断是否是第一次使用该应用程序
      * 
      * */
    public static boolean isFirstUse(Context context)
    {
    	SharedPreferences sharedPreferences = context.getSharedPreferences(WHAT_IS_NEW_PRE_NAME, Activity.MODE_PRIVATE);
        boolean flag = sharedPreferences.getBoolean(FIRST_USE_FLAG, true);
        return flag;
    }
    
    /**
     * save the flag of first use the application
     * 
     * 保存第一次使用的信息
     * 
     * */
    public static void saveFirstUseFlag(Context context)
    {
    	SharedPreferences sharedPreferences = context.getSharedPreferences(WHAT_IS_NEW_PRE_NAME, Activity.MODE_PRIVATE);
        SharedPreferences.Editor editor = sharedPreferences.edit();
        editor.putBoolean(FIRST_USE_FLAG, false);
        editor.commit();
    }
    
}
