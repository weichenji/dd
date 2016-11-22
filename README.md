  
##网格视图（GrideView）<br>
<hr>
  　　 <h3> 如果是列表（单列多行形式）的使用ListView，如果是`多行多列`网状形式的优先使用`GridView。`<h2><br>
<hr>
使用步骤：<br>
　　　　　　　1、准备数据源<br>
　　　　　　　2、新建适配器<br>
　　　　　　　3、加载适配器<br>
<hr>
实例解析：<br> 
 main.xml<br>
<?xml version="1.0" encoding="utf-8"?><br>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"<br>
    android:orientation="vertical"<br>
    android:layout_width="fill_parent"<br>
    android:layout_height="fill_parent"<br>
    ><br>
    <GridView      <br>
        android:id="@+id/GridView1"  <br>
        android:layout_width="wrap_content"  <br>
        android:layout_height="wrap_content"<br>
        android:columnWidth="90dp"<br>
        android:numColumns="3" <br>
        android:verticalSpacing="10dp"<br>
        android:horizontalSpacing="10dp"<br>
        android:stretchMode="columnWidth"<br>
        android:gravity="center"     <br>    
        /><br>
</LinearLayout>
