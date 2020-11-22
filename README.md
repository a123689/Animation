# Animation
 Animation resource: Xây dựng các hiệu ứng chuyển đổi cho các đối tượng view
 
 Phân loai Animation resource
 
 -Property animation
 
 -View animation
 
  +Tween Animation (Alpha,Rotate,Scale,Translate)
  
  +Frame Animation
  
  # Property animation
  
  Tạo một animation bằng cách sửa đổi các giá trị thuộc tính đối tượng trong khoang thời gian nhất định với animator
  
   <objectAnimator android:propertyName="y"
        android:valueFrom="0"
        android:valueTo="500"
        android:duration="2000"
        android:startOffset="1000"
        android:repeatMode="restart"
        android:repeatCount="infinite"
        />
        
  val anim = AnimatorInflater.loadAnimator(this,R.animator.property_animation)
        anim.setTarget(tvImage)
        anim.start()      
