Overview
=============

Because App Cloud is built on top of web technologies, integrating Double Click for Publishers (DFP) ads into an App Cloud app is straightforward.  Below are the steps you will need to follow in order to integrate an ad into your template that when tapped will open in a module window.  For convenience we also provide a full working template which can be found in the the example directory.

What you need
=============

* The embed code retrieved from [https://www.google.com/dfp/]DFP for this Ad Unit.
  * This embed code should have a target platform of "mobile". 
  * The embed code should have type of "Site" rather then "Application".
  * This can be any size you want, but we using a 320x50 ad for this example.
* Access to your App Cloud application code base or ability to run scaffolding script.
* Workshop installed on a smart phone to test the application.

Integration
=============

Open the HTML file for each view for which you would like to serve an ad and paste the script tag provided by DFP for your header into the header.  In our example code the script tags look like:

    <script type='text/javascript'>
    (function() {
    var useSSL = 'https:' == document.location.protocol;
    var src = (useSSL ? 'https:' : 'http:') +
    '//www.googletagservices.com/tag/js/gpt_mobile.js';
    document.write('<scr' + 'ipt src="' + src + '"></scr' + 'ipt>');
    })();
    </script>
    <script type='text/javascript'>
    googletag.cmd.push(function() {
    googletag.defineSlot('/6390/App-Cloud-Example', [320, 50], 'div-gpt-ad-1341933272661-0').addService(googletag.pubads());
    googletag.enableServices();
    });
    </script>

With in your HTML page decide where you would like to place your ad unit and paste the code snippet provided by DFP for your document body into it.  In our example we paste the code below between the header and the scrollable area.

    <script type='text/javascript'>
    (function() {
    var useSSL = 'https:' == document.location.protocol;
    var src = (useSSL ? 'https:' : 'http:') +
    '//www.googletagservices.com/tag/js/gpt_mobile.js';
    document.write('<scr' + 'ipt src="' + src + '"></scr' + 'ipt>');
    })();
    </script>
    <script type='text/javascript'>
    googletag.cmd.push(function() {
    googletag.defineSlot('/6390/App-Cloud-Example', [320, 50], 'div-gpt-ad-1341933272661-0').addService(googletag.pubads());
    googletag.enableServices();
    });
    </script>

Screenshot
============

![Screenshot](https://dl.dropbox.com/u/9478378/ad-example.png)