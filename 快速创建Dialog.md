# 快速创建Dialog

### 1. 创建自己的Dialog组件

```java
public class MyDialog extends Dialog {

    private Context context;

    //构造函数,可以自己给定参数（content是必须的）
    public MyDialog(@NonNull Context context) {
        super(context);
        this.context = context;
    }

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.mydialog);
        
        //若是dialog中有按钮，点击事情写在oncreate里面
        
    }
}

```

### 2. Activity中调用

```java
btnShowDialog=findViewById(R.id.btn_show_dialog);
btnShowDialog.setOnClickListener((v)->{
    MyDialog dialog = new MyDialog(MainActivity.this);
    dialog.show();
});
```

点击事件中调用即可，传入参数的时候根据构造函数来，context是必须的。