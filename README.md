  
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
 　   android:layout_width="fill_parent"<br><br>
　    android:layout_height="fill_parent"
　    ><br>
 　   <GridView //gridView布局 <br>
　        android:id="@+id/GridView1"  <br>
 　       android:layout_width="wrap_content"  <br>
 　       android:layout_height="wrap_content"<br>
 　       android:columnWidth="90dp"//每列的宽度，也就是Item的宽度<br>
  　      android:numColumns="3"//列数设置设为3列<br>
 　       android:verticalSpacing="10dp"//垂直边距<br>
 　       android:horizontalSpacing="10dp"//水平边距<br>
　        android:stretchMode="columnWidth"//缩放模式<br>
 　       android:gravity="center" <br>        
 　       /><br>
</LinearLayout><br>
<hr>
MainActivity.Java<br>
...<br>

public class MainActivity extends Activity { <br>
 　   @Override <br>
 　   public void onCreate(Bundle savedInstanceState) {  <br>
 　       super.onCreate(savedInstanceState);  <br>
  　      setContentView(R.layout.main);  <br>
  　      GridView gv = (GridView)findViewById(R.id.GridView1);  <br>
   　     //为GridView设置适配器  <br>
  　      gv.setAdapter(new MyAdapter(this));  <br>
 　       //注册监听事件  <br>
 　       gv.setOnItemClickListener(new OnItemClickListener()  <br>
 　       {  <br>
 　           public void onItemClick(AdapterView<?> parent, View v, int position, long id)  <br>
  　          {  <br>
　                Toast.makeText(MainActivity.this, "pic" + position, Toast.LENGTH_SHORT).show();  <br>
 　           }  <br>
　        });  <br>
　    }  <br>
}  <br> 
