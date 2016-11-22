  
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
  　      GridView gv = (GridView)findViewById(R.id.GridView1); //加载布局 <br>
   　     //为GridView设置适配器  <br>
  　     ` gv.setAdapter(new MyAdapter(this));` //设置适配器 <br>
 　       //注册监听事件  <br>
 　       gv.setOnItemClickListener(new OnItemClickListener()  <br>
 　       {  <br>
 　           public void onItemClick(AdapterView<?> parent, View v, int position, long id)  <br>
  　          {  <br>
　               ` Toast`.makeText(MainActivity.this, "pic" + position, Toast.LENGTH_SHORT).show(); //使用Toast显示 <br>
 　           }  <br>
　        });  <br>
　    }  <br>
}  <br> 
<hr>
 //自定义适配器 <br>
  　  class MyAdapter extends `BaseAdapter`{//创建适配器继承自子类`BaseAdapter` <br>
     　   //上下文对象 <br>
     　   private` Context` context;//含有一个私有对象context <br>
     　   //图片数组 <br>
     　   private` Integer[] imgs` = {  //imgs数组用来加载图片 ！注意：格式<br>
            　    R.drawable.pic0, R.drawable.pic1, R.drawable.pic2,  <br>
              　  R.drawable.pic3, R.drawable.pic4, R.drawable.pic5,   <br>             
             　   R.drawable.pic6, R.drawable.pic7, R.drawable.pic8,  <br>
              　  R.drawable.pic0, R.drawable.pic1, R.drawable.pic2,  <br>
              　  R.drawable.pic3, R.drawable.pic4, R.drawable.pic5,   <br>             
              　  R.drawable.pic6, R.drawable.pic7, R.drawable.pic8, <br>
   　     };<br>
         //MyAdapter的构造器含有一个context参数；<br>
      　  MyAdapter(Context context){ <br>
          　  this.context = context; <br>
     　   } <br>
         //三个方法‘getCount’‘getItem’‘getItemId’
      　  public int `getCount()` { <br>
          　  return imgs.length; 
    　    } <br>
 
      　  public Object `getItem(int item) `{ <br>
           　 return item; 
      　  } <br>
 
      　  public long` getItemId(int id)` { <br>
           　 return id; 
    　  　  } <br>
<hr>
: getView(int position, View convertView, ViewGroup parent)方法，当列表中每一项显示到页面时， 都会调用Adapter的getView方法返回一个View<br>
  　 //创建View方法 <br>
     　   public View getView(int position, View convertView, ViewGroup parent) { <br>
        　     `ImageView` imageView; <br>
           　     if (convertView == null) { <br>
             　       imageView = new ImageView(context); //给ImageView设置资源<br>
              　      imageView.setLayoutParams(new GridView.LayoutParams(75, 75));//设置布局图片7575显示 <br>
               　     imageView.setAdjustViewBounds(false);//设置边界对齐 <br>
               　     imageView.setScaleType(ImageView.ScaleType.CENTER_CROP);//设置刻度的类型 <br>
                　    imageView.setPadding(8, 8, 8, 8);//设置间距 <br>
            　    }  <br>
              　  else { <br>
             　       imageView = (ImageView) convertView; <br>
            　    } <br>
             　   imageView.setImageResource(imgs[position]);//为ImageView设置图片资源 <br>
              　  return imageView; <br>
      　  } <br>
} <br>
     
