# Automated tests for PhpFox using Selenium IDE

In an effort to improve the quality of our software we are starting to use Selenium IDE for automatic tests. 
The approach I am taking is to work on a bug report and write a test case while fixing it, then publish the test case to this repository and link to it in the bug report, maybe my test case is bugged and someone else can improve it.

HTML files are test cases unless they have the word "suite" in the file name, in which case its a Test Suite (collection of test cases).

Some test cases may require the [goto_sel_ide.js](http://www.seleniumhq.org/docs/02_selenium_ide.jsp#goto-sel-ide-js-extension) extension, which [is included in this repository](https://raw.github.com/purefan/tesenfox/master/goto_sel_ide.js) to make sure it remains available, so its a good idea to install it anyways.

Following you will find an index of the test cases published and a description of each case:

## AdminCP
* [Clear Cache](admincp/clear_cache_suite.html): This is a test suite. It goes to the AdminCP and clears cache from there.

## Event

* [Test 1](event/374_event_1.html): Due to the many cache settings adding an event may not show in the core.index-member controller in the birthdays block. This test checks that adding, and deleting an event refreshes the cache, and shows the event and removes it accordingly.
* [Test 2](feed/1): Checks that adding a series of hashtags separated by a line break does not corrupt the hashtag with the line break tag (for example: #hashtag<br). This case uses the utility case "Clear Cache" (mentioned below), update this suite when Clear Cache is updated.

## Utility Cases
These cases are used in more than one suite.
* [Clear Cache](admincp/clear_cache.html): Clears the site cache, assumes we are already in the AdminCP. Requires [this test case](admincp/go_to_admincp.html).
* [Go to AdminCP](admincp/go_to_admincp.html): Takes the user to the AdminCP, if it needs to log to the AdminCP it attempts log in with an arbitrary user.