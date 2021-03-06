# UIC Helper Methods 
Helper methods for Android Mobile Application Development

```java
    /* ###########  UIC Helper Methods  ###########  */

    public void uicActivityFullScreen(){
        requestWindowFeature(Window.FEATURE_NO_TITLE);
        this.getWindow().setFlags(WindowManager.LayoutParams.FLAG_FULLSCREEN, WindowManager.LayoutParams.FLAG_FULLSCREEN);
        getSupportActionBar().hide();
	/* Usage: Call method before setContentView(args) method. */
    }

    public void uicToastMessage(String message){
        Toast.makeText(this, message ,Toast.LENGTH_SHORT).show();
    }

    public void uicHideKeyboard(){
        InputMethodManager imm = (InputMethodManager)getSystemService(Context.INPUT_METHOD_SERVICE);
        imm.hideSoftInputFromWindow(getCurrentFocus().getWindowToken(),InputMethodManager.RESULT_UNCHANGED_SHOWN);
    }
    
    public void uicSplashBasic(){
        new Handler().postDelayed(new Runnable() {
            @Override
            public void run() {
                startActivity(new Intent(SplashActivity.this,MainActivity.class));
                finish();
            }
        }, 3000);
	/*Usage: Make sure to follow class names assigned.*/
    }    

    /* ###########  UIC Helper Methods  ###########  */
```

### Usage
* Place all or selected codes (depends on usage) inside any Java Class that extends Activity Class.
* If you are using Android Studio, you may use shortcut keys Alt + Ins (Windows) to import necessary packages/libraries.

### Sample Usage

```java
/* MainActivity.java */

...

	public class MainActivity extends AppCompatActivity {
		@Override
		protected void onCreate(Bundle savedInstanceState) {
			super.onCreate(savedInstanceState);
			uicActivityFullScreen();
			setContentView(R.layout.activity_main);
		}
	}

	public void uicActivityFullScreen(){
		requestWindowFeature(Window.FEATURE_NO_TITLE);
		this.getWindow().setFlags(WindowManager.LayoutParams.FLAG_FULLSCREEN, WindowManager.LayoutParams.FLAG_FULLSCREEN);
		getSupportActionBar().hide();
	}

...

```
