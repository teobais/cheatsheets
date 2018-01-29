### Hot Reload
Case: code changes are not reflected in Tomcat
Possible cause: tomcat's and/or browser's cache is not cleaned up
Solution(s): 1) clear browser cache, 2) check the "Disable cache" option in Network tab of Developer Tools of your browser, 3) ensure `work\Catalina\localhost` of your Tomcat installation is clean
