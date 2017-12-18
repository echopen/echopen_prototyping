# Member variables:

	private Button scanButton;
	private ImageView resultImageView;
 
### Use full name for variable names:
 
	Bundle arguments = new Bundle();
 
Instead of:
    
	Bundle args = new Bundle();
	

**Note:** *We code also for humans and not only machine ;).*
    
# Constants:

### Usage of SNAKE_CASE    

	public static final int SCAN_RESULT_CODE = 10;
	public static final String RESULT_DATA_KEY = "result";
    
### Apply prefix on constants related to bundle, intents, argments or shared preferences:
    
	Bundle : BUNDLE_
	Intent Extra : EXTRA_
	Intent Action : ACTION_
	Argument fragment : ARGUMENT_
	SharedPreferences : PREF_
    
_E.g._
    
	private static final String PREF_EMAIL = "PREF_EMAIL";
	private static final String BUNDLE_AGE = "BUNDLE_AGE";
    
# Class naming:
    
For class name use the Pascal Case.    
    
	MainActivity.java			-> activity_main.xml
	SplashScreenActivity.java	-> activity_splashscreen.xml
	ScanBodyFragment.java		-> fragment_scan_body.xml
	
**Note:** *You should not take care about the name of your xml files. 
There will be automatically generated when you will create a new Activity of fragment using Android Studio.* 

# Activity / Fragment names

The name of your activities or fragments should always finish respectively by Activity or Fragment. 
	
    
# XML identifiers :
    
Use the semantic *component\_function* to make your identifiers easier to find or more suggestive.
    
	<Button
		android:id="@+id/button_scan"
		android:layout_width="wrap_content"
		android:layout_height="wrap_content" />
		
	<TextView
		android:id="@+id/textview_result_detail"
		android:layout_width="wrap_content"
		android:layout_height="wrap_content" />
	    
# Methods:

When writing methods please use the camel Case.    

	private int getResult() { … }
	private void displayImage(Image image) { … }
    
# Block if:
    
	if (myValue == 1) {
	    
	} else if (myValue == 2) {
	    
	} else {
	    
	}
