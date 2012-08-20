package com.michael.component.whatisnew;

import java.util.ArrayList;
import java.util.List;

import android.app.Activity;
import android.content.Context;
import android.support.v4.view.ViewPager;
import android.support.v4.view.ViewPager.OnPageChangeListener;
import android.util.AttributeSet;
import android.view.LayoutInflater;
import android.view.View;
import android.view.animation.Animation;
import android.view.animation.Animation.AnimationListener;
import android.view.animation.AnimationUtils;
import android.widget.ImageView;
import android.widget.LinearLayout;
import android.widget.TextView;

/**
 * This class encapsulate the View which used for introduce something new of your application,
 * or how to use your application etc to users.Of course,you can also encapsulate this in a Activity,
 * but if you do that, you can not achieve the effect of animations perfectly.
 * So,I decide to encapsulate this in a LinearLayout(View).Because most animations 
 * can be achieve perfectly in the same Activity,not between two Activity. 
 * You can do this by use the method setContentView();
 * 
 * setContentView(R.layout.activity_main);
 * setContentView(new WhatIsNewView(context));
 * just switch these method dynamic in the same Activity MainActivity.java.
 * 
 * 
 * 
 * 一般应用程序第一次使用的时候，都有一个关于你的程序的新特性，或者任何是任何使用你的程序的介绍等等。
 * 你可以把这个功能封装在一个Activity里面，但是这样做有一点不好的地方，当你要实现一些动画效果的时候，
 * 在Activity之间实现起来不是很完美，会闪一下，为了实现类似微信那样的效果，我们需要将它封装为一个View
 * 也就是说和程序的主界面在同一个Activity中，通过setContentView方法来切换视图，这样就可以较好的实现效果
 * 而且不需要在Manifest中申明一个Activity，也方便使用。
 * 
 * @author Michael 叶坤
 * 
 * @since 2012-08-07
 * */
public class WhatIsNewView extends LinearLayout {

	private Context context;
	private ImageView ivLeftImage;
	private ImageView ivRightImage;
	private TextView tvLeftButton;
	private TextView tvRightButton;
	private DotMarks dotViews;
	
	public WhatIsNewView(Context context, AttributeSet attrs) {
		super(context, attrs);
		this.context = context;
		ini(context);
	}

	public WhatIsNewView(Context context) {
		super(context);
		this.context = context;
		ini(context);
	}

	private void ini(Context context)
	{
		LayoutInflater mInflater = ((Activity)context).getLayoutInflater();
		View layoutWhatIsNew = mInflater.inflate(R.layout.layout_what_is_new, null);
		View viewPagerOne = mInflater.inflate(R.layout.viewpager_one, null);
		View viewPagerTwo = mInflater.inflate(R.layout.viewpager_two, null);
        View viewPagerThree = mInflater.inflate(R.layout.viewpager_three, null);
        View viewPagerFour = mInflater.inflate(R.layout.viewpager_four, null);
        View viewPagerFive = mInflater.inflate(R.layout.viewpager_five, null);
        ViewPager viewPager = (ViewPager)layoutWhatIsNew.findViewById(R.id.view_pager);
        List<View> viewItems = new ArrayList<View>();
        viewItems.add(viewPagerOne);
        viewItems.add(viewPagerTwo);
        viewItems.add(viewPagerThree);
        viewItems.add(viewPagerFour);
        viewItems.add(viewPagerFive);
        viewPager.setAdapter(new WhatIsNewAdapter(viewItems));
        dotViews = (DotMarks)layoutWhatIsNew.findViewById(R.id.dot_marks);
        viewPager.setOnPageChangeListener(new OnPageChangeListener() {
			
        	/**
        	 * Update the marks when viewPager's index changed
        	 * 根据ViewPager的页面的变化来实时更新索引小图标
        	 * 
        	 * */
			@Override
			public void onPageSelected(int arg0) {
				dotViews.updateMark(arg0);
			}
			
			@Override
			public void onPageScrolled(int arg0, float arg1, int arg2) {
				
			}
			
			@Override
			public void onPageScrollStateChanged(int arg0) {
				
			}
		});
        
        ivLeftImage = (ImageView)viewPagerFive.findViewById(R.id.iv_left_image01);
        ivRightImage = (ImageView)viewPagerFive.findViewById(R.id.iv_left_image02);
        LinearLayout llStartApp = (LinearLayout)viewPagerFive.findViewById(R.id.ll_start_app);
        tvLeftButton = (TextView)viewPagerFive.findViewById(R.id.tv_left_btn01);
        tvRightButton = (TextView)viewPagerFive.findViewById(R.id.tv_left_btn02);
        llStartApp.setOnClickListener(new OnClickListener() {
			
        	/**
        	 * Here you can do some animations and finish this Activity 
        	 * 
        	 * 这里你可以执行一些界面切换的动画，并finish这个Activity
        	 *
        	 * */
			@Override
			public void onClick(View v) {
				startAnimation();
			}
		});
        
        this.addView(layoutWhatIsNew);
        
	}

	
	/**
	 * startAnimation
	 * 
	 * 开始动画
	 * 
	 * */
	private void startAnimation()
	{
		Animation leftAnim = AnimationUtils.loadAnimation(context, R.anim.slide_left_anim);
		Animation rightAnim = AnimationUtils.loadAnimation(context, R.anim.slide_right_anim);
		final Animation fadeAnim = AnimationUtils.loadAnimation(context, R.anim.fade_anim);
		leftAnim.setFillAfter(true);
		rightAnim.setFillAfter(true);
		rightAnim.setAnimationListener(new AnimationListener() {
			
			@Override
			public void onAnimationStart(Animation animation) {
				if(onAnimListener != null)
				{
					onAnimListener.onAnimationStart();
					dotViews.startAnimation(fadeAnim);
				}
			}
			
			@Override
			public void onAnimationRepeat(Animation animation) {
				
			}
			
			@Override
			public void onAnimationEnd(Animation animation) {
				if(onAnimListener != null)
				{
					onAnimListener.onAnimationEnd();
				}
			}
		});
		ivLeftImage.startAnimation(leftAnim);
		tvLeftButton.startAnimation(leftAnim);
		ivRightImage.startAnimation(rightAnim);
		tvRightButton.startAnimation(rightAnim);
	}
	
	private OnAppAnimationListener onAnimListener;
	
	/**
	 * Here add a listener,to listen the event of animation started and ended.
	 * 
	 * 这里设置一个监听，当动画开始和结束的时候通知外面setContentView改变
	 * 
	 * */
	public interface OnAppAnimationListener
	{
		public void onAnimationStart();
		
		public void onAnimationEnd();
	}
	
	public void setOnAppAnimationListener(OnAppAnimationListener onAnimListener)
	{
		this.onAnimListener = onAnimListener;
	}
}




























