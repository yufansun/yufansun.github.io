---
layout: post
title:  "Background Execution Swift"
date:   2016-04-14 23:45:17 -0400
categories: Swift
---
Using Swift, the current execution state of an app is available from `UIApplication.sharedApplication().applicationState`.

# Downloading and uploading in the background with NSURLSession
~~~
*    Enabling `NSURLSession` to be background-capable requires instantiating a `NSURLSessionConfiguration` object with the background initializer and an identifier that’s reused for all background sessions:


{% highlight swift %}
let sessionConfig = NSURLSessionConfiguration.backgroundSessionConfigurationWithIdentifier("com.newrelic.bgt")
{% endhighlight %}

~~~
# Downloading remote content opportunistically
* background fetch—a kind of smart, per-app crontab that wakes up at opportunistic times. iOS checks how much data and battery power was used during previous background fetches when scheduling future callbacks.


Check out the [blog][blog] [iOS Developer Library][iOS-developer-library]for more info.

[blog]: https://blog.newrelic.com/2016/01/13/ios9-background-execution/
[iOS-developer-library]: https://developer.apple.com/library/ios/documentation/iPhone/Conceptual/iPhoneOSProgrammingGuide/BackgroundExecution/BackgroundExecution.html