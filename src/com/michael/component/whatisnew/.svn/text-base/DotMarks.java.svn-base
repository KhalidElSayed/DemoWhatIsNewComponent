package com.michael.component.whatisnew;

import android.app.Activity;
import android.content.Context;
import android.graphics.drawable.Drawable;
import android.util.AttributeSet;
import android.view.LayoutInflater;
import android.view.View;
import android.widget.ImageView;
import android.widget.LinearLayout;

/**
 * This class is used to wrap the dot marks which displayed in the bottom of the View
 * 这个类将底部的显示页面索引的小标记包装起来
 * 
 * @author Michael 叶坤
 * @since 2012-08-07
 * */
public class DotMarks extends LinearLayout
{

	public DotMarks(Context context, AttributeSet attrs) {
		super(context, attrs);
		ini(context);
	}

	public DotMarks(Context context) {
		super(context);
		ini(context);
	}

	private ImageView viewOne;
	private ImageView viewTwo;
	private ImageView viewThree;
	private ImageView viewFour;
	private ImageView viewFive;
	
	private void ini(Context context)
	{
		LayoutInflater mInflater = ((Activity)context).getLayoutInflater();
		View dotViews = mInflater.inflate(R.layout.dot_marks, null);
		this.addView(dotViews);
		viewOne = (ImageView)dotViews.findViewById(R.id.iv_one);
		viewTwo = (ImageView)dotViews.findViewById(R.id.iv_two);
		viewThree = (ImageView)dotViews.findViewById(R.id.iv_three);
		viewFour = (ImageView)dotViews.findViewById(R.id.iv_four);
		viewFive = (ImageView)dotViews.findViewById(R.id.iv_five);
		
		//initialize the dots
		viewOne.setImageDrawable(whiteDot);
		viewTwo.setImageDrawable(darkDot);
		viewThree.setImageDrawable(darkDot);
		viewFour.setImageDrawable(darkDot);
		viewFive.setImageDrawable(darkDot);
	}
	
	/**
	 * display the dot marks dynamic by the viewPager index which passed in
	 * 
	 * 根据传递进来的页面的索引切换小图标的显示
	 * 
	 * */
	private Drawable whiteDot = this.getResources().getDrawable(R.drawable.dot_white);
	private Drawable darkDot = this.getResources().getDrawable(R.drawable.dot_dark);
	public void updateMark(int index)
	{
		switch(index)
		{
		case 0:
			viewOne.setImageDrawable(whiteDot);
			viewTwo.setImageDrawable(darkDot);
			viewThree.setImageDrawable(darkDot);
			viewFour.setImageDrawable(darkDot);
			viewFive.setImageDrawable(darkDot);
			break;
		case 1:
			viewOne.setImageDrawable(darkDot);
			viewTwo.setImageDrawable(whiteDot);
			viewThree.setImageDrawable(darkDot);
			viewFour.setImageDrawable(darkDot);
			viewFive.setImageDrawable(darkDot);
			break;
		case 2:
			viewOne.setImageDrawable(darkDot);
			viewTwo.setImageDrawable(darkDot);
			viewThree.setImageDrawable(whiteDot);
			viewFour.setImageDrawable(darkDot);
			viewFive.setImageDrawable(darkDot);
			break;
		case 3:
			viewOne.setImageDrawable(darkDot);
			viewTwo.setImageDrawable(darkDot);
			viewThree.setImageDrawable(darkDot);
			viewFour.setImageDrawable(whiteDot);
			viewFive.setImageDrawable(darkDot);
			break;
		case 4:
			viewOne.setImageDrawable(darkDot);
			viewTwo.setImageDrawable(darkDot);
			viewThree.setImageDrawable(darkDot);
			viewFour.setImageDrawable(darkDot);
			viewFive.setImageDrawable(whiteDot);
			break;
		}
	}
}













