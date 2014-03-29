##  Trying out Firebase (Beta) hosting solution and good example of Firebase Security rules 

Since Firebase now offers a [Beta hosting service](https://www.firebase.com/docs/hosting.html) (and I was looking for a quick way to publish one of the firebase PoCs I'm working at the moment), I decided to take it for a spin.

I have to say that I'm really impressed with the end result, and as you will see below, there entire process (from install to published website) was really smooth.  


  


Note 1: in the example below I already had created an Firebase app to hold the data (see [Using Firebase to sync data with a webpage (via Javascript, REST and Firebase Admin panel)](http://blog.diniscruz.com/2014/02/using-firebase-to-sync-data-with.html) for details on how to create one) 

  


Note 2: at the time I wrote this post, the website created is/was (depending on when you are reading this) hosted at [https://tm-admin-test.firebaseapp.com/](https://tm-admin-test.firebaseapp.com/)

  


Starting with the instructions from [Firebase hosting](https://www.firebase.com/docs/hosting.html) page:

****  
**  
**

[![](images/Screen_Shot_2014-02-27_at_16_55_18.png)](http://2.bp.blogspot.com/-mbjRZjEjh3M/Uw9ucL7drsI/AAAAAAAAH68/_vmVzF2Yuaw/s1600/Screen+Shot+2014-02-27+at+16.55.18.png)

  


1) Install the firebase tools

  


  


[![](images/Screen_Shot_2014-02-27_at_17_01_47.png)](http://1.bp.blogspot.com/-OKdFaWfIT80/Uw9vn9LD7eI/AAAAAAAAH7U/JEw_-sh0_uw/s1600/Screen+Shot+2014-02-27+at+17.01.47.png)

 ....

[![](images/Screen_Shot_2014-02-27_at_17_02_06.png)](http://4.bp.blogspot.com/-00qYi8Gndw4/Uw9vn0kLYfI/AAAAAAAAH7Y/efkek80KQYs/s1600/Screen+Shot+2014-02-27+at+17.02.06.png)

**  
**

**2) Run the firebase BootStrap**

  


[![](images/Screen_Shot_2014-02-27_at_16_33_55.png)](http://1.bp.blogspot.com/-aLive0hUzPQ/Uw9uSOaFHpI/AAAAAAAAH4Q/_jKRnvNn3dY/s1600/Screen+Shot+2014-02-27+at+16.33.55.png)

  
... after logging in (above), we are asked to chose the 'firebase' app to use (below)

[![](images/Screen_Shot_2014-02-27_at_16_34_17.png)](http://1.bp.blogspot.com/-uA0xh1jKr0U/Uw9uSOJvanI/AAAAAAAAH4Y/sZbxaZs0fCo/s1600/Screen+Shot+2014-02-27+at+16.34.17.png)

  
... then pick the template to use (I chose the **_angular_** one)

[![](images/Screen_Shot_2014-02-27_at_16_34_37.png)](http://3.bp.blogspot.com/-a0eMhui73nI/Uw9uSGPaPiI/AAAAAAAAH4U/PO_pawb-bto/s1600/Screen+Shot+2014-02-27+at+16.34.37.png)

  
 ... and that's it:

[![](images/Screen_Shot_2014-02-27_at_16_35_02.png)](http://1.bp.blogspot.com/-Elz7FlHAZ1c/Uw9uS6WIsKI/AAAAAAAAH4o/wGy6ajJhgtE/s1600/Screen+Shot+2014-02-27+at+16.35.02.png)

  
Here are the files created locally (all under the **_tm-admin-test_** folder)

[![](images/Screen_Shot_2014-02-27_at_16_36_28.png)](http://2.bp.blogspot.com/-lwSLLLfQ_Zk/Uw9uVuCOBFI/AAAAAAAAH44/RCJ7j5VQ6SQ/s1600/Screen+Shot+2014-02-27+at+16.36.28.png)

**3) Deploy the application**

[![](images/Screen_Shot_2014-02-27_at_16_37_20.png)](http://1.bp.blogspot.com/-e5yfiP2SnrQ/Uw9uV4aw4vI/AAAAAAAAH5A/-6gy_D8-QfU/s1600/Screen+Shot+2014-02-27+at+16.37.20.png)

  
... which is also super quick.

After completion the default browser is opened with the created website, which looked like this:

[![](images/Screen_Shot_2014-02-27_at_16_40_48.png)](http://3.bp.blogspot.com/-WUztZVDHh4w/Uw9uVya9bDI/AAAAAAAAH48/m8xIMgwBzlk/s1600/Screen+Shot+2014-02-27+at+16.40.48.png)

  
**4) Testing the test app**  
**  
**The created/published test app has a simple [Firebase 3-way data binding](https://www.firebase.com/blog/2013-10-04-firebase-angular-data-binding.html) example, where changes in an **_angular-binded _**model, are propagated to the server, and distributed to any connected clients (the image below shows two browsers and the firebase admin panel, all synced in real time (regardless where the data is changed))  
**  
**  


[![](images/Screen_Shot_2014-02-27_at_16_42_24.png)](http://3.bp.blogspot.com/-kjttDs9399U/Uw9uWu5KObI/AAAAAAAAH5Q/RNg3PMpcsjc/s1600/Screen+Shot+2014-02-27+at+16.42.24.png)

  
There is a basic **Chat **page:

[![](images/Screen_Shot_2014-02-27_at_16_43_55.png)](http://2.bp.blogspot.com/-wqYNhCQUBkc/Uw9uXcfXAHI/AAAAAAAAH5c/zZO-X0NObrU/s1600/Screen+Shot+2014-02-27+at+16.43.55.png)

  
... which allows new messages to be added and viewed in real time:

[![](images/Screen_Shot_2014-02-27_at_16_44_04.png)](http://1.bp.blogspot.com/-4tFNMxCmkgE/Uw9uZ9fm_aI/AAAAAAAAH6M/MDscensFFU4/s1600/Screen+Shot+2014-02-27+at+16.44.04.png)

  
Also included is a Login page (with account creation capabilities):

[![](images/Screen_Shot_2014-02-27_at_16_44_46.png)](http://4.bp.blogspot.com/-JrUiOJiJWYA/Uw9uXvU4NLI/AAAAAAAAH5k/qGt_r8FnZyM/s1600/Screen+Shot+2014-02-27+at+16.44.46.png)

  


**5) Review the security rules**

**  
**

At this stage it's good to take a look at the security rules added to this Firebase app.

  


In the image below we can see that:

  * Anonymous users **_can_** **_read_** all data, but **_not write_** by default
  * The **_syncedValue_** object **_can be read and written_** by all

    * there is a validation on this field that ensures that it is not empty and not bigger that 100 chars

  * The **_messages_** object (i.e. 'firebase section/subdomain'):

    * can be read by all
    * each message must include a property called_ text _with a max length of 1000 chars
    * (I think) the **_.validate = false_** means that no other properties can be added

  * the **_users_** object:

    * each **_$user_** child object:

      * can be read if the current user matches its name (i.e. it is logged in as that user)
      * each user can write into two fields: _**name**_ and **_email_** (both with a max length of 2000) 

  


[![](images/Screen_Shot_2014-02-27_at_16_42_49.png)](http://1.bp.blogspot.com/-u72ssmlmuSc/Uw9uXJGOA5I/AAAAAAAAH5U/3MEWOKtoZzc/s1600/Screen+Shot+2014-02-27+at+16.42.49.png)

  
**6) Create an account**  
**  
**To test the provided authorisation solution, let's start by trying to login with an account that doesn't exist:

[![](images/Screen_Shot_2014-02-27_at_16_44_58.png)](http://2.bp.blogspot.com/-OWkQ8tqpTPM/Uw9uYNZaCiI/AAAAAAAAH5s/nwgLpCADo8I/s1600/Screen+Shot+2014-02-27+at+16.44.58.png)

  
 ... then click on the **_Register_** button (which just adds a **_confirm pass_** field)

[![](images/Screen_Shot_2014-02-27_at_16_45_54.png)](http://2.bp.blogspot.com/-ketb0wZXt18/Uw9uYVUsb-I/AAAAAAAAH50/6OvDu9qOxwk/s1600/Screen+Shot+2014-02-27+at+16.45.54.png)

  
Here is what the 'post register/login' page looks like (note that the top-menu-bar **_login_** link was also changed to **_account_**)

[![](images/Screen_Shot_2014-02-27_at_16_46_27.png)](http://3.bp.blogspot.com/--GaJw_nbTbo/Uw9uY-VhVsI/AAAAAAAAH58/-MTOSgE8SCM/s1600/Screen+Shot+2014-02-27+at+16.46.27.png)

Clicking on _home_ takes us to the first page, which also shows a different message (now that we are logged in)

[![](images/Screen_Shot_2014-02-27_at_16_46_57.png)](http://3.bp.blogspot.com/-zhoQ_0_BvqY/Uw9uZd7eh9I/AAAAAAAAH6E/Mm1zep2f0pQ/s1600/Screen+Shot+2014-02-27+at+16.46.57.png)

  
Interestingly the **_Chat_** page doesn't seem to take into account that we are logged in now (would be nice to show the current user in the message posted)

[![](images/Screen_Shot_2014-02-27_at_16_47_20.png)](http://3.bp.blogspot.com/-E6XcbYvT1ms/Uw9ucI_29RI/AAAAAAAAH64/4xj8KyxO6cY/s1600/Screen+Shot+2014-02-27+at+16.47.20.png)

  
**6) Take a look at data (as stored in the assigned Firebase app)**  
**  
**Using the control panel for the current app:

a) here is the **_syncedValue_** object

[![](images/Screen_Shot_2014-02-27_at_16_47_32.png)](http://1.bp.blogspot.com/-UCUJUivPObM/Uw9uZ8w1B_I/AAAAAAAAH6U/vtK-EUZJ9Wo/s1600/Screen+Shot+2014-02-27+at+16.47.32.png)

  
b) here is the **_messages_** object (which is a firebase kind-of-array, based on a name/value pair. The name is the **_node_** text (for example_ -JGoCMZRRGo1WQHmYxmc_) and the value is the child _text_ node value (for example _test _)):

[![](images/Screen_Shot_2014-02-27_at_16_47_53.png)](http://4.bp.blogspot.com/-v9ZG4rQksPA/Uw9uae0F9AI/AAAAAAAAH6g/xwOXQICdGtA/s1600/Screen+Shot+2014-02-27+at+16.47.53.png)

  
c) There was a new **_users_** node/object in the root of the app's data:

[![](images/Screen_Shot_2014-02-27_at_16_48_38.png)](http://1.bp.blogspot.com/-FSMPouXO3A4/Uw9uax1qEJI/AAAAAAAAH6k/jH3bK8ZLhd4/s1600/Screen+Shot+2014-02-27+at+16.48.38.png)

  
... which contains the user provided (and 'editable by that user') data (_email_ and _name_)

[![](images/Screen_Shot_2014-02-27_at_16_48_47.png)](http://3.bp.blogspot.com/-aFxEdfAnMlk/Uw9ubRcOr0I/AAAAAAAAH6s/uYFg2IpZUtg/s1600/Screen+Shot+2014-02-27+at+16.48.47.png)

  
And where is the user's credentials?

The user created was added to the current list of 'registered users' , and it must be stored somewhere inside firebase servers since we don't have access to it (hopefully it is stored using a nice strong hashing algorithm)

[![](images/Screen_Shot_2014-02-27_at_16_49_07.png)](http://2.bp.blogspot.com/-rirUGiqaY6o/Uw9ubvbYr4I/AAAAAAAAH7I/Hhe1WPnlNZw/s1600/Screen+Shot+2014-02-27+at+16.49.07.png)

  
**Wrapping up**  
**  
**Kudos to the Firebase team for providing such easy-to-use hosting solution (next step for me is to try to use it in the TeamMentor PoC I'm currently working on)  
**  
**For reference the AngularJS+Firebase website that was created by the Firebase cli tool, is the one available at [https://github.com/firebase/angularFire-seed](https://github.com/firebase/angularFire-seed) (which contains a nice **README.md **file with more details)

  


[![](images/Screen_Shot_2014-02-27_at_17_32_30.png)](http://1.bp.blogspot.com/-JndUE9QxzTE/Uw94WgzE7jI/AAAAAAAAH7s/yons7BhJWCw/s1600/Screen+Shot+2014-02-27+at+17.32.30.png)

  

