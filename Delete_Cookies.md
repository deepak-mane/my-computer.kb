

# Here's a command-line solution for deleting specific cookies from Chrome.
Cookies are stored in an sqlite database file:
```
on Linux: ~/.config/google-chrome/Default/Cookies
on Windows: %LOCALAPPDATA%\Google\Chrome\User Data\Default\Cookies
on Mac: ~/Library/Application Support/Google/Chrome/Default/Cookies
```
You can delete all cookies belonging to a site by running an SQL DELETE command on this file:

Linux / Mac
```
sqlite3 cookiefile 'DELETE FROM cookies WHERE host_key LIKE "%domain%";'
```
Windows
```
sqlite3 cookiefile "DELETE FROM cookies WHERE host_key LIKE '%domain%';"
```
Note:
You can download the sqlite commandline client from here: https://sqlite.org/download.html


Perhaps the easiest way to view your cookies in Chrome is to visit:

chrome://settings/cookies
This does not allow you to edit the cookies in Google Chrome 33.0.1750.117 (Official Build 252094) on Mac OS X, but does allow viewing and deleting.

Update (2017-08-08) [verified in 59.0.3071.115 (Official Build) (64-bit)]
In more recent versions, cookies are listed at:

chrome://settings/content/cookies
Update (2018-03-01) [Google Chrome 64.0.3282.167 (Official Build) (64-bit)]
To see the content you will need to select "See all cookies and site data" or follow...

chrome://settings/siteData
