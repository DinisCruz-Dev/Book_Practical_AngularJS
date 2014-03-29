##  Debugging a weird case of missing module in AngularJS and KarmaJS 

When I was trying the  [Running KarmaJS's AngularJS example test/e2e/angular-scenario (on Chrome)](http://blog.diniscruz.com/2013/06/running-karmas-angularjs-example.html) I hit on the the following weird behaviour.

TLDR; the solution was to run **_npm install --g _****_karma@canary_**  
  
**Setup**  
**  
**Chrome window opened in:

[![image](images/image_thumb_25255B4_25255D1.png)](http://lh3.ggpht.com/-gOnNRpYO97k/Ub8e8uhBqbI/AAAAAAAAOGU/wPWUvIoVA6Q/s1600-h/image%25255B8%25255D.png)

... a local website at port 8000:

[![image](images/image_thumb_25255B5_25255D1.png)](http://lh6.ggpht.com/-_laPjPIUgSc/Ub8e-HRG1KI/AAAAAAAAOGk/abj6VBYsgg8/s1600-h/image%25255B9%25255D.png)

... which is a nodeJS powered website, started using **_node server.js_** (below)

[![image](images/image_thumb_25255B13_25255D1.png)](http://lh5.ggpht.com/-VDWxVtk_FMc/Ub8lLdqcs_I/AAAAAAAAOG8/XdCk6fuvPsE/s1600-h/image%25255B23%25255D.png)

A simple (as I could make it)**_ Karma.config.js _**file

[![image](images/image_thumb_25255B14_25255D1.png)](http://lh6.ggpht.com/-2TqzSiJwIG4/Ub8lMxUbfuI/AAAAAAAAOHM/x3X6BK4evXM/s1600-h/image%25255B24%25255D.png)

.... and AngularJS test

[![image](images/image_thumb_25255B15_25255D1.png)](http://lh4.ggpht.com/-VbIgWhcnL_0/Ub8lOOI808I/AAAAAAAAOHc/JGgfCLYAUJY/s1600-h/image%25255B25%25255D.png)   
**  
****Scenario A) Running from folder with karma clone (and npm install)**  
**  
****_karma start ..\angular-scenario\karma.conf.js _**works OK

[![image](images/image_thumb_25255B16_25255D.png)](http://lh4.ggpht.com/-EjSAz4pB2MI/Ub8lQTn_mdI/AAAAAAAAOHs/vMJIFUb_XWk/s1600-h/image%25255B28%25255D.png)

**Scenario B) running from parent folder**  
**  
****_karma start angular-scenario\karma.conf.js _**fails with a **_module is not defined error_**  
**_  
_**[![image](images/image_thumb_25255B17_25255D1.png)](http://lh4.ggpht.com/-4sk8_OwZxfQ/Ub8lR1hpwUI/AAAAAAAAOH8/TsUYoGn2_Fg/s1600-h/image%25255B31%25255D.png)

So what I think is happening is that because I run**_ npm install_** on the karma folder (the one I got from a GitHub clone), there are more modules in there than in the global karma (which I got when I installed karma using **_npm install --g karma_**)

At the moment there are 49 modules in the GitHub karma:

[![image](images/image_thumb_25255B21_25255D1.png)](http://lh3.ggpht.com/-28mDTv7SVXQ/Ub8lTuoBekI/AAAAAAAAOIM/8eeRbliwhew/s1600-h/image%25255B39%25255D.png)

And 20 modules in the global karma install

[![image](images/image_thumb_25255B19_25255D1.png)](http://lh3.ggpht.com/-ZGmAOXdwQYg/Ub8lWF0PsVI/AAAAAAAAOIc/nSwuLOG3g68/s1600-h/image%25255B35%25255D.png)

So let's try running npm install on this folder

[![image](images/image_thumb_25255B23_25255D1.png)](http://lh5.ggpht.com/-1L0omjoPhVI/Ub8lXzGaffI/AAAAAAAAOIs/EaEWLKnBQmY/s1600-h/image%25255B45%25255D.png)   
[![image](images/image_thumb_25255B22_25255D1.png)](http://lh5.ggpht.com/-6cZkFSSrISg/Ub8lZrebu7I/AAAAAAAAOI8/-I9lM-y0_MQ/s1600-h/image%25255B42%25255D.png)

And now there are 33 modules installed:

[![image](images/image_thumb_25255B25_25255D1.png)](http://lh5.ggpht.com/-dmT-kK7bi94/Ub8lcMQF2cI/AAAAAAAAOJM/1Rbx-sk-YN0/s1600-h/image%25255B49%25255D.png)

but that still didn't work :(

At this stage I remembered reading something about installing the latest version of karma (globally), which is probably what I'm getting from the github clone, and that could explain the different number of modules.

So I executed **_npm install --g _****_karma@canary_**  
**_  
_**[![image](images/image_thumb_25255B26_25255D1.png)](http://lh3.ggpht.com/-1QDfSXVYr_s/Ub8ld7S8EKI/AAAAAAAAOJc/7XCb__VPQKU/s1600-h/image%25255B52%25255D.png)   
which installed ok:  
[![image](images/image_thumb_25255B27_25255D1.png)](http://lh4.ggpht.com/-hYAyB6Quuao/Ub8lfEe43EI/AAAAAAAAOJs/JtTiuWywdTs/s1600-h/image%25255B55%25255D.png)

Now runnig the **scenario B) **case throws a different error:

[![image](images/image_thumb_25255B28_25255D1.png)](http://lh4.ggpht.com/-mYjlJalc3RI/Ub8lgoduTFI/AAAAAAAAOJ8/fZ5TBB2dbBk/s1600-h/image%25255B58%25255D.png)

It looks that we also need install the **_karma-ng-scenario_** module

[![image](images/image_thumb_25255B29_25255D1.png)](http://lh4.ggpht.com/-LwklqvPhnMw/Ub8ljIs8UBI/AAAAAAAAOKM/dj8uDDeafcw/s1600-h/image%25255B61%25255D.png)

And now it works :)

[![image](images/image_thumb_25255B30_25255D1.png)](http://lh5.ggpht.com/-55OmX_u74ng/Ub8lkhtb1GI/AAAAAAAAOKc/fa9DtFGR_2w/s1600-h/image%25255B64%25255D.png)





- - - - 
[Table of Contents](../Table_of_contents.md) | [Code](../Code)