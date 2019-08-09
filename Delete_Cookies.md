

# Here's a command-line solution for deleting specific cookies from Chrome.
Cookies are stored in an sqlite database file:

on Linux: ~/.config/google-chrome/Default/Cookies
on Windows: %LOCALAPPDATA%\Google\Chrome\User Data\Default\Cookies
on Mac: ~/Library/Application Support/Google/Chrome/Default/Cookies
You can delete all cookies belonging to a site by running an SQL DELETE command on this file:

Linux / Mac

sqlite3 cookiefile 'DELETE FROM cookies WHERE host_key LIKE "%domain%";'
Windows

sqlite3 cookiefile "DELETE FROM cookies WHERE host_key LIKE '%domain%';"
Note:
You can download the sqlite commandline client from here: https://sqlite.org/download.html
