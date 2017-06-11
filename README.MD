* 欢迎关注微信公众号、长期为您推荐优秀博文、开源项目、视频

* 微信公众号名称：Android干货程序员

* ![](http://upload-images.jianshu.io/upload_images/4037105-8f737b5104dd0b5d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![Logo](images/example.png)

Example
--------
Generate the following style:

![NewY York](images/newyork.png)

### 第一步. 在项目的根目录build.gradle添加依赖

~~~
allprojects {
    repositories {
       ......
        maven { url "https://jitpack.io" }
    }
}

~~~
![](http://upload-images.jianshu.io/upload_images/4037105-2faa5daca3bfe8a0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 第二步.  在Module的build.gradle添加依赖

~~~
compile 'com.github.open-android:EmphasisTextView:0.1.0'
~~~

### 第三步：初始化TextView：
```
<babushkatext.BabushkaText
        android:id="@+id/text"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:background="#DFF1FE"
        android:padding="5dp"/>
```
### 第四步：实现上图效果，拷贝如下代码：
```
public class MainActivity extends ActionBarActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Display "9.5 excellent!"
        final BabushkaText babushka1 = (BabushkaText)findViewById(R.id.text);
        babushka1.addPiece(new BabushkaText.Piece.Builder("  9.5  ")
                .backgroundColor(Color.parseColor("#073680"))
                .textColor(Color.WHITE)
                .build());
        babushka1.addPiece(new BabushkaText.Piece.Builder(" excellent! ")
                .backgroundColor(Color.parseColor("#DFF1FE"))
                .textColor(Color.parseColor("#073680"))
                .style(Typeface.BOLD)
                .build());
        babushka1.display();

        // Display "3.4 horrible!"
        final BabushkaText babushka2 = (BabushkaText)findViewById(R.id.text2);
        babushka2.addPiece(new BabushkaText.Piece.Builder("  3.4  ")
                .backgroundColor(Color.parseColor("#800736"))
                .textColor(Color.WHITE)
                .build());
        babushka2.addPiece(new BabushkaText.Piece.Builder(" horrible! ")
                .backgroundColor(Color.parseColor("#fedfe2"))
                .textColor(Color.parseColor("#800736"))
                .style(Typeface.BOLD)
                .build());
        babushka2.display();

        // Display "starting at $420"
        BabushkaText babushka3 = (BabushkaText)findViewById(R.id.text3);
        babushka3.addPiece(new BabushkaText.Piece.Builder("starting at ")
                .textColor(Color.parseColor("#50AF2C"))
                .build());
        babushka3.addPiece(new BabushkaText.Piece.Builder("$420!")
                .textColor(Color.parseColor("#50AF2C"))
                .textSizeRelative(1.2f)
                .style(Typeface.BOLD)
                .build());
        babushka3.display();

        // Display "nightly price"
        BabushkaText babushka4 = (BabushkaText)findViewById(R.id.text4);
        babushka4.addPiece(new BabushkaText.Piece.Builder("nightly price  ")
                .textColor(Color.parseColor("#5F5F5F"))
                .superscript()
                .textSizeRelative(0.9f)
                .style(Typeface.BOLD)
                .build());
        babushka4.addPiece(new BabushkaText.Piece.Builder("$256")
                .textColor(Color.parseColor("#5F5F5F"))
                .superscript()
                .strike()
                .textSizeRelative(0.9f)
                .style(Typeface.BOLD)
                .build());
        babushka4.addPiece(new BabushkaText.Piece.Builder(" $179")
                .textColor(Color.parseColor("#9E0719"))
                .textSizeRelative(1.5f)
                .style(Typeface.BOLD)
                .build());
        babushka4.display();

        // Display "new York"
        BabushkaText babushka5 = (BabushkaText)findViewById(R.id.text5);
        babushka5.addPiece(new BabushkaText.Piece.Builder("New York, United States\n")
                .textColor(Color.parseColor("#414141"))
                .style(Typeface.BOLD)
                .build());
        babushka5.addPiece(new BabushkaText.Piece.Builder("870 7th Av, New York, Ny\n")
                .textColor(Color.parseColor("#969696"))
                .textSizeRelative(0.9f)
                .style(Typeface.BOLD)
                .build());
        babushka5.addPiece(new BabushkaText.Piece.Builder("10019, United States of America")
                .textColor(Color.parseColor("#969696"))
                .textSizeRelative(0.8f)
                .build());
        babushka5.display();

        // Display "Central Park"
        BabushkaText babushka6 = (BabushkaText)findViewById(R.id.text6);
        babushka6.addPiece(new BabushkaText.Piece.Builder("Central Park, NY\n")
                .textColor(Color.parseColor("#414141"))
                .build());
        babushka6.addPiece(new BabushkaText.Piece.Builder("1.2 mi ")
                .textColor(Color.parseColor("#0081E2"))
                .textSizeRelative(0.9f)
                .build());
        babushka6.addPiece(new BabushkaText.Piece.Builder("from here")
                .textColor(Color.parseColor("#969696"))
                .textSizeRelative(0.9f)
                .build());
        babushka6.display();

        // Display "Bryant Park Hotel"
        BabushkaText babushka7 = (BabushkaText)findViewById(R.id.text7);
        babushka7.addPiece(new BabushkaText.Piece.Builder("The Bryant Park Hotel\n")
                .textColor(Color.parseColor("#414141"))
                .build());
        babushka7.addPiece(new BabushkaText.Piece.Builder("#6 of 434 ")
                .textColor(Color.parseColor("#0081E2"))
                .build());
        babushka7.addPiece(new BabushkaText.Piece.Builder("in New York City\n")
                .textColor(Color.parseColor("#969696"))
                .build());
        babushka7.addPiece(new BabushkaText.Piece.Builder("2487 reviews\n")
                .textColor(Color.parseColor("#969696"))
                .build());
        babushka7.addPiece(new BabushkaText.Piece.Builder("$540")
                .textColor(Color.parseColor("#F7B53F"))
                .style(Typeface.BOLD)
                .build());
        babushka7.addPiece(new BabushkaText.Piece.Builder(" per night")
                .textColor(Color.parseColor("#969696"))
                .build());
        babushka7.display();

        findViewById(R.id.button).setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                BabushkaText.Piece aPiece = babushka1.getPiece(0);
                aPiece.setText("  9.9  ");
                babushka1.display();
            }
        });
    }

}
```

### 支持的样式?
--------
可以用下面的方法定制你的文字风格，其内部被转换成相应的` spannables ` 

| Babushka Method        | Internal Span           |
| ------------- |:-------------:|
| textSize      | AbsoluteSizeSpan |
| textColor      | ForegroundColorSpan      |
| textSizeRelative | RelativeSizeSpan      |
| backgroundColor | BackgroundColorSpan      |
| style | StyleSpan      |
| underline | UnderlineSpan      |
| strike | StrikethroughSpan      |
| superscript | SuperscriptSpan      |
| subscript | SubscriptSpan      |

### 我还能做什么？ 
--------
一旦你创建和显示你的babushkatext，你可以修改每个单独文本呢内容。例如，如果我们想把上面例子中的“1.2个MI”改为‘1.9公里’，我们可以做以下操作： 

```java
// grab the Piece at position 1
Piece piece = babushka.getPiece(1);

// modify it's text
piece.setText("1.9 km ");

// you must always call display after you alter a Piece's text
babushka.display();
```

