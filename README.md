#Intercom iphone module for Intercom IOS SDK version 2.3.19

Test Environment
========

Titanium Mobile SDK 5.2.1.GA.
iOS SDK 9.3
Intercom IOS SDK Version 2.3.19


## License

    The MIT License (MIT) Copyright © 2015

    Permission is hereby granted, free of charge, to any person obtaining a copy
    of this software and associated documentation files (the "Software"), to deal
    in the Software without restriction, including without limitation the rights
    to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
    copies of the Software, and to permit persons to whom the Software is
    furnished to do so, subject to the following conditions:

    The above copyright notice and this permission notice shall be included in
    all copies or substantial portions of the Software.

    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
    IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
    FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
    AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
    LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
    OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
    THE SOFTWARE.


##Installation for Mac OS X
###Step 1
Download the project.
Copy the ti.intercom.ios-iphone-[version].zip into your Titanium SDK directory: http://docs.appcelerator.com/titanium/latest/#!/guide/Titanium_Modules

Update modules section of your tiapp.xml like below:

    <modules>
        <module platform="iphone">ti.intercom.ios</module>
    </modules>


###Step 2
Project clean.
Copy TiIntercom\assets\Intercom.bundle to the project folder app\assets\iphone
Run Titanium project.

###Step 3
[More Information](https://github.com/intercom/intercom-ios)

EXAMPLEs
========
	// Require the module
	var TiIntercom = require('ti.intercom.ios');

	// Initialize intercom with api_key and api_id
	TiIntercom.initialize({
	    api_key: '<#ios_sdk-...#>',
	    app_id: '<#your-app-id#>'
	});
	
    // Login with ID
	TiIntercom.registerUserWithUserId(user._id);

	// Login with user email
	TiIntercom.registerUserWithEmail("<#user@email.com#>");

	// Log event with name
	TiIntercom.logEventWithName("<#eventName#>")

	// Log event with name and data
	// Intercom does not buffer log during offline
	TiIntercom.logEventWithNameAndData({
		'name':'<#eventName#>',
		'date':'<#date#>',
		'data':'<#data#>'
	})

    // Update attributes
    TiIntercom.updateUserWithAttributes({
		user_id : user._id,
		email : user.email,
		created_at : user.DateCreated,
		name : user.profile.fname + " " + user.profile.lname
	});

    // Register for Push Notifications
    TiIntercom.setDeviceToken(deviceToken);

