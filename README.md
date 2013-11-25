# Automated tests for PhpFox using Selenium IDE

In an effort to improve the quality of our software we are starting to use Selenium IDE for automatic tests. 
The approach I am taking is to work on a bug report and write a test case while fixing it, then publish the test case to this repository and link to it in the bug report, maybe my test case is bugged and someone else can improve it.

The structure for this repository is pretty straightforward, there are folders for each of the modules and each test case has this name convention:
`<phpfox-version>_<module>_<counter>.html`

The version for which the test case was created, followed by the module (to make it easier to readh when exporting) and a sequential number. Since a test case may apply to many bug reports there is no point in including them in the file name.

Following you will find an index of the test cases published and a description of each case:

## Event

* [Test 1](event/374_event_1.html): Due to the many cache settings adding an event may not show in the core.index-member controller in the birthdays block. This test checks that adding, and deleting an event refreshes the cache, and shows the event and removes it accordingly.