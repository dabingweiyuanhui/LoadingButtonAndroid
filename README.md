
[ ![Download](https://api.bintray.com/packages/lehen01/maven/loading-button/images/download.svg) ](https://bintray.com/lehen01/maven/loading-button/_latestVersion)[![Build Status](https://travis-ci.org/leandroBorgesFerreira/LoadingButtonAndroid.svg?branch=master)](https://travis-ci.org/leandroBorgesFerreira/LoadingButtonAndroid)

# Progress Button Android

![enter image description here](https://i.stack.imgur.com/8SHR1.gif)

Android Button that morphs into a loading progress bar. 

  - Fully customizable in the XML
  - Really simple to use.
  - Makes your app looks cooler =D

You can check how this library was implemented here: https://medium.com/p/9efee6e39711/

## Contents

 - [Installation](#installation)
 - [How to use / Sample](#how-to-use)
	 - [Animate and revert animation](#animate-and-revert-animation)
	 -  [Show done animation](#show-done-animation)
	 - [Revert the loading animation with different text or image](#revert-the-loading-animation-with-different-text-or-image)
 - [Configure XML](#configure-xml)
 - [Be Creative](#be-creative)
 - [Wanna Contribute?](#wanna-contribute)
 - [Bugs and feedback](#bugs-and-feedback)
 - [Credits](#credits)

## Installation

    compile 'br.com.simplepass:loading-button-android:1.6.6'

## How to use

### Animate and revert animation

Add the button in your layout file and customize it the way you like it.

      <br.com.simplepass.loading_button_lib.customViews.CircularProgressButton
        	    android:id="@+id/btn_id"
        	    android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:background="@drawable/circular_border_shape"
                app:spinning_bar_width="4dp" <!-- Optional -->
                app:spinning_bar_color="#FFF" <!-- Optional -->
                app:spinning_bar_padding="6dp" <!-- Optional -->

Then, instanciate the button

        CircularProgressButton btn = (CircularProgressButton) findViewById(R.id.btn_id)

        btn.startAnimation();
        
    [do some async task. When it finishes]
    //You can choose the color and the image after the loading is finished
		btn.doneLoagingAnimation(fillColor, bitmap); 
		[or just revert de animation]
		btn.revertAnimation();

### - Show 'done' animation

When the loading animation is running, call:

    //Choose the color and the image that will be show
    circularProgressButton.doneLoagingAnimation(fillColor, bitmap);
		
### - Revert the loading animation with different text or image

    circularProgressButton.revertAnimation(new OnAnimationEndListener() {
                    @Override
                    public void onAnimationEnd() {
                        circularProgressButton.setText("Seu texto aqui!");
                    }
                });
or

    circularProgressImageButton.revertAnimation(new OnAnimationEndListener() {
            @Override
            public void onAnimationEnd() {
                progressButton.setImageDrawable(R.drawable.image);
            }
        });

## Configure XML

 - app:spinning_bar_width : Changes the width of the spinning bar inside the button
 - app:spinning_bar_color: Changes the color of the spinning bar inside the button
 - app:spinning_bar_padding: Changes the padding of the spinning bar in relation of the button bounds. 
 - app:initialCornerAngle: The initial corner angle of the animation. Insert 0 if you have a square button. 
 - app:finalCornerAngle: The final corner angle of the animation.


## Be creative!

You can do a lot of fun stuff with this lib. Check this example:

![enter image description here](https://lh3.googleusercontent.com/-jJeS1G1mrBY/WBNosRmWSqI/AAAAAAAAKbM/NxWA09f0XqcutIO2VW8RDPhwW1CPRebWQCLcB/s0/out-28-2016+12-55-20.gif "out-28-2016 12-55-20.gif")

You can find the code for the animation inside this repo.


## Wanna contribute?

If you had some idea for this library and want you contribute, please send me an email: lehen01@gmail.com

## Bugs and Feedback

For bugs, feature requests, and discussion please use [GitHub Issues](https://github.com/leandroBorgesFerreira/LoadingButtonAndroid/issues).

## Credits

This libs was inspired in this repo: https://github.com/dmytrodanylyk/android-morphing-button
    
### And that's it! Enjoy!
