## Steps to integrate sdk in your project
1. Open your app.gradle of your project, add the following dependencies.
```
compile('com.rollbar:rollbar-java:1.0.1')
compile('com.rollbar:rollbar-android:1.0.1@aar')
```
2. Add the project access token from step 1 in your manifest file under application section. You can find manifest file in your project directory.
```
<meta-data android:name="com.rollbar.android.ACCESS_TOKEN" android:value="ACCESS_TOKEN" />
```
3. Initialize Rollbar in the launcher activity
```
Rollbar.init(this);
```

## Example Code.
```
import com.rollbar.android.Rollbar;

public class MainActivity extends AppCompatActivity {

    private Button button;
    private Rollbar rollbar;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        button=(Button)findViewById(R.id.clickMe);
        Rollbar.init(this);
        button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                if (rollbar == null) {
                    Log.d("yo", "Rollbar is null, initialize before using");
                    return;
                }
                String test=null;
                test.toString();
            }
        });
    }
}
```


