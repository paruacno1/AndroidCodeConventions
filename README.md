## AndroidCodeConventions
Hey guys,

Here are some coding conventions for Android and Java. These are based upon the Code Style Guidelines for Contributors by Google.

### I do not claim that this is my original work but yes, it includes my study of Google Guidelines, my experience of writing code with colleagues and facing problems.


Why I am writing this - 

To make the code writing consiting atleast on a small level. We have global style rules and generally all the programmers follow those but still we need some internal conventions so that it does not impact the other contributors in an organization.

## First rule of Jumping into any running project
**BE CONSISTENT - **
If you are trying to edit code. Before start take few minutes to look at the code around you or go through some code snippets in the project. Try to identify the standards like if they have used spaces around the if statements, if they put asteriks(*) to show separation, so you should do that too.

The main idea behind having the style guidelines is to have the common vocabulary of wiriting code. If some code is added in a file look different from the existing code around it, it breaks the concentration of the reader (contributor). Try to avoid this.

### Java Rules:

#### Variable Naming Conventions

* Non - static, non public field names should start with a lower case letter.

* Static field names start with a lower case letter.

* Other fields start with a lower case letter.

* Public static final fields (constants) are ALL_CAPS_WITH_UNDERSCORES.

* All the lower case letter naming conventions should follow the Camel Case rule.

Example:

    public class MyExample {
        public static final int ANY_CONSTANT = 007;
        public int publicIntVariable;
        private static String = Example.class.getSimpleName();
        private int privateIntVariable;
        protected int protectedIntVariable;
    }

#### Try Using Standard Braces Style
Braces should be put on the same line.

Example:

    class MyExample {
        private int anyMethod() {
            if (something) {
                // do something...
            } else if (somethingElse) {
                // do something...
            } else {
                // do something...
            }
        }
    }
        
We require braces around the statements for a conditional. Except, if the entire conditional (the condition and the body) fit on one line, you may (but are not obligated to) put it all on one line. That is, this is good:

    if (condition) {
        body(); //good practice...
    }
    
and this is good:

    if (condition) body(); //good practice..
    
but this is still bad:

    if (condition)
        body();  // bad practice !!..
        
        


#### In Naming Conventions, treat abbreviations / acronyms as words:

|Good|Bad|
|:--:|:--:|
|getCustomerId|getCustomerID|
|class Html|class HTML|
|String url|String URL|
|long id|long ID|

#### Using TODO Comments makes your life easier:

Use TODO comments for code that is temporary, a short-term solution, or good-enough but not perfect and you wish to fix it in future. Also, don't hesitate to put your name with the TODO so that it acts as a reminder for you and the other contributors that who has to look at it and who marked it as a TODO. 

How to use - 
TODOs should include the string TODO in all caps, followed by a colon:

        // TODO: Try to reduce time complexity later - by Ankit.

and

        // TODO: Remove the static string use dynamic data - added by Ankit, should be fixed by SomeName .

If your TODO is of the form "At a future date do something" make sure that you either include a very specific date ("Fix by November 2005") or a very specific event ("Remove this code after all production mixers understand protocol V7.").


#### Always write access modifiers.

We all know what are the access modifiers but sometimes in hurry we don't feel important to mention it against all the fields. Please don't ignore this. This is very important.
  
Example:

    public class MyExample {
        public static final int ANY_CONSTANT = 007;
        public int publicIntVariable;
        private static String = Example.class.getSimpleName();
        private int privateIntVariable;
        protected int protectedIntVariable;
    }
    

#### Never write an empty method and if it is much needed, write a comment why.
Example:

        /**
        * @return int value
        */
        private int anyMethod() {
            // Will write the implementation in future when needed
        }



#### Write Short Methods

Try keeping the methods small and focused. However, it recognised that long methods are sometimes appropriate, so no hard limit is there on the method length. But if a method exceeds 40-50 lines, think about breaking it in to small methods withouth affecting the structure of the program. The small chunks of code is easier to understand, increases readability and looks good.

#### Define Fields in Standard Places

Fields should be defined either at the top of the file. Do not delcare variables where the methods are written. All the global fields should be on top of the file.



### Android Resource Style Rules

Name the files in such a way that if they are sorted alphabetically, all the related assets will group together.

All resources should be categorised which makes it easier to search for a resource and to understand what the resource is being used for.

#### Animation Resources

    animation_<name>.xml
    
Example:

    animation_fade_in.xml

#### Drawable Resources

    drawable_<name>_background.xml
    drawable_<name>_pressed.xml
    drawable_<name>_normal.xml
    drawable_<name>_default.xml
    drawable_<name>_selector.xml


|Asset Type|Prefix|Example|
|:--:|:--:|:--:|
|Icons|ic_|ic_tick.png|
|Launcher icons|ic_|ic_launcher.png|
|Menu icons and Action Bar icons|ic_menu|ic_menu_settings.png|

#### Layout Resources

It helps to use a common prefix for each type of layout xml file. For instances layout xml files for an activity should be preceded with "activity_", below is some examples of this.

        activity_<activity_name>.xml
        
        fragment_<fragment_name>.xml

        list_item_<category_name>.xml

        dialog_<category_name>.xml

        map_<category_name>.xml

It also helps to use a prefix for the id's based on their usage;. Below are some examples of id's;

LinearLayout id :

        android:id="@+id/ll_<name>"

RelativeLayout id :

        android:id="@+id/rl_<name>"

FrameLayout id :

        android:id="@+id/fl_<name>"

Fragment id :

        android:id="@+id/f_<name>"

