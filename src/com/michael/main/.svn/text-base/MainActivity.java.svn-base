package com.michael.main;

import android.app.Activity;
import android.os.Bundle;
import android.view.LayoutInflater;
import android.view.View;
import android.view.animation.Animation;
import android.view.animation.AnimationUtils;

import com.michael.component.whatisnew.R;
import com.michael.component.whatisnew.WhatIsNewUtils;
import com.michael.component.whatisnew.WhatIsNewView;
import com.michael.component.whatisnew.WhatIsNewView.OnAppAnimationListener;

/**
 * 
 * This is the MainActivity of the Application
 * 
 * 这个是程序的主界面
 * 
 * @author Michael 叶坤
 * @since 2012-08-07
 * */
public class MainActivity extends Activity {

    @Override
    public void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        									//judge the application is first used
        									//判断是否是第一次使用
        if(WhatIsNewUtils.isFirstUse(MainActivity.this))
        {
        	showWhatIsNew();
        }
        else
        {
        	setContentView(R.layout.activity_main);//normally
        }
        
    }
    
    /**
     * show something about you application
     * 
     * 显示关于你的程序的介绍
     * */
    private void showWhatIsNew()
    {
    	WhatIsNewView whatIsNewView = new WhatIsNewView(MainActivity.this);
    	whatIsNewView.setOnAppAnimationListener(new OnAppAnimationListener() {
			
			@Override
			public void onAnimationStart() {
				
			}
			
			@Override
			public void onAnimationEnd() {
				LayoutInflater mInflater = MainActivity.this.getLayoutInflater();
	    		final View mainActivityView = mInflater.inflate(R.layout.activity_main, null);
				setContentView(mainActivityView);
				Animation enterAnim = AnimationUtils.loadAnimation(MainActivity.this, R.anim.main_activity_enter_anim);
				enterAnim.setFillAfter(true);
				mainActivityView.startAnimation(enterAnim);
			}
		});
    	setContentView(whatIsNewView);
    	
    	//save the flag ,so next time when user open this application,WhatIsNewUtils.isFirstUse(MainActivity.this) will return false
    	//保存标记，下一次打开程序WhatIsNewUtils.isFirstUse(MainActivity.this)返回的是false
    	WhatIsNewUtils.saveFirstUseFlag(MainActivity.this);
    }

}




















