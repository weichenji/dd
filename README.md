  
##网格视图（GrideView）<br>
<hr>
  　　 <h3> 如果是列表（单列多行形式）的使用ListView，如果是`多行多列`网状形式的优先使用`GridView。`<h2><br>
<hr>
使用步骤：<br>
　　　　　　　1、准备数据源<br>
　　　　　　　2、新建适配器<br>
　　　　　　　3、加载适配器<br>
<hr>
   
main.xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="fill_parent"
    android:layout_height="fill_parent"
    >
    <GridView  
        android:id="@+id/GridView1"  
        android:layout_width="wrap_content"  
        android:layout_height="wrap_content"
        android:columnWidth="90dp"
        android:numColumns="3"
        android:verticalSpacing="10dp"
        android:horizontalSpacing="10dp"
        android:stretchMode="columnWidth"
        android:gravity="center"         
        />
</LinearLayout>
