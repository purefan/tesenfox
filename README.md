# Automated tests for PhpFox using Selenium IDE

In an effort to improve the quality of our software we are starting to use Selenium IDE for automatic tests. 
The approach I am taking is to work on a bug report and write a test case while fixing it, then publish the test case to this repository and link to it in the bug report, maybe my test case is bugged and someone else can improve it.

HTML files are test cases unless they have the word "suite" in the file name, in which case its a Test Suite (collection of test cases).

Some test cases may require the [goto_sel_ide.js](http://www.seleniumhq.org/docs/02_selenium_ide.jsp#goto-sel-ide-js-extension) extension, which [is included in this repository](https://raw.github.com/purefan/tesenfox/master/goto_sel_ide.js) to make sure it remains available, so its a good idea to install it anyways.

Following you will find an index of the test cases and suites published and a description of each case:

## AdminCP
* [Clear Cache](admincp/test_suites/clear_cache.html): This is a test suite. It goes to the AdminCP and clears cache from there.

## Event
* [Test 1](event/test_cases/add_new_event.html): Due to the many cache settings adding an event may not show in the core.index-member controller in the birthdays block. This test checks that adding, and deleting an event refreshes the cache, and shows the event and removes it accordingly.
* [Test 2](feed/test_cases/assert_hashtag1.html): Checks that adding a series of hashtags separated by a line break does not corrupt the hashtag with the line break tag (for example: #hashtag<br).

** Feed
* [Test hashtag in russian](feed/test_suites/test_hashtag_in_russian.html): Adds a couple of status updates with a Russian word (provided by a client), clears cache and visits the page to list items with that hashtag, at least one item must exit.

## Utility Cases
These cases are used in more than one suite.
* [Go to AdminCP](admincp/test_cases/go_to_admincp.html): Takes the user to the AdminCP, if it needs to log to the AdminCP it attempts log in with an arbitrary user.
* [Clear Cache](admincp/test_cases/clear_cache.html): Clears the site cache, assumes we are already in the AdminCP. Requires [this test case](admincp/go_to_admincp.html).
* [Enable Hashtags](admincp/test_cases/enable_hashtags.html): Assumes the location is already the AdminCP and enables hashtags.