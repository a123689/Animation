# Animation
 Animation resource: Xây dựng các hiệu ứng chuyển đổi cho các đối tượng view
 
 Phân loai Animation resource
 
 -Property animation
 
 -View animation
 
  +Tween Animation (Alpha,Rotate,Scale,Translate)
  
  +Frame Animation
  
  # Property animation
  
  Tạo một animation bằng cách sửa đổi các giá trị thuộc tính đối tượng trong khoang thời gian nhất định với animator
  
  xml
  
   android:ordering="sequentially"
  objectAnimator android:propertyName="y"
        android:valueFrom="0"
        android:valueTo="500"
        android:duration="2000"
        android:startOffset="1000"
        android:repeatMode="restart"
        android:repeatCount="infinite"
        
        
  val anim = AnimatorInflater.loadAnimator(this,R.animator.property_animation)
        anim.setTarget(tvImage)
        anim.start()      
  
  kotlin
   val objectanimator = ObjectAnimator.ofFloat(tvImage, View.Y,0f,400f)
        objectanimator.setDuration(2000)
        objectanimator.repeatMode =ValueAnimator.REVERSE
        objectanimator.repeatCount = ValueAnimator.INFINITE
        objectanimator.startDelay = 1000

        val animatorset = AnimatorSet()
        animatorset.play(objectanimator)
        animatorset.start()
        
 # Tween Animation       
        
        alpha
        
        alpha android:fromAlpha="1"
        android:toAlpha="0.2"
        android:duration="1000"
        android:startOffset="1000"
        android:repeatMode="reverse"
        android:fillAfter="true"
        android:repeatCount="infinite"
        
        val animation = AnimationUtils.loadAnimation(this,R.anim.alpha)
        tvImage.startAnimation(animation)
        
        
        mutil animation
        
        val animation1 =  AnimationUtils.loadAnimation(this,R.anim.translate)
        val animation2 = AnimationUtils.loadAnimation(this,R.anim.translate)
        val animationset = AnimationSet(false)
        animationset.addAnimation(animation1)
        animationset.addAnimation(animation2)
        
        
        frame
        
       <animation-list xmlns:android="http://schemas.android.com/apk/res/android">

    <item android:drawable="@drawable/ic_launcher_background"/>
    <item android:drawable="@drawable/ic_launcher_background"/>
    <item android:drawable="@drawable/ic_launcher_background"/>
     </animation-list>
        
        tvImage.setBackgroundResource(R.drawable.frame_list)
        val anim = tvImage.background as AnimationDrawable
        anim.start()
