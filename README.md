# Automated tests for PhpFox using Selenium IDE

In an effort to improve the quality of our software we are starting to use Selenium IDE for automatic tests. 
The approach I am taking is to work on a bug report and write a test case while fixing it, then publish the test case to this repository and link to it in the bug report, maybe my test case is bugged and someone else can improve it.

The structure for this repository is pretty straightforward, there are folders for each of the modules and each test case has this name convention:
`<phpfox-version>_<module>_<counter>.html`

The version for which the test case was created, followed by the module (to make it easier to readh when exporting) and a sequential number. Since a test case may apply to many bug reports there is no point in including them in the file name.

Following you will find an index of the test cases published and a description of each case:

## Event

* [Test 1](event/374_event_1.html): Due to the many cache settings adding an event may not show in the core.index-member controller in the birthdays block. This test checks that adding, and deleting an event refreshes the cache, and shows the event and removes it accordingly.
* [Test 2](feed/1): Checks that adding a series of hashtags separated by a line break does not corrupt the hashtag with the line break tag (for example: #hashtag<br). This case uses the utility case "Clear Cache" (mentioned below), update this suite when Clear Cache is updated.

## Utility Cases
These cases are used in more than one suite.
* [Clear Cache](admincp/clear_cache.html): Clears the site cache by going to the AdminCP. Requires an admin user logged in and may fail if the admin user is required to log in to the AdminCP. the FlowControl plugin may be required to improve this case.