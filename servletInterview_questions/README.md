# Interview questions
# 21) What is load-on-startup in servlet?
The load-on-startup element of servlet in web.xml is used to load the servlet at the time of deploying the project or server start. So it saves time for the response of first request.
# 22) What if we pass negative value in load-on-startup?
It will not affect the container, now servlet will be loaded at first request.
# 23) What is war file?
A war (web archive) file specifies the web elements. A servlet or jsp project can be converted into a war file. Moving one servlet project from one place to another will be fast as it is combined into a single file.
# 24) How to create war file?
The war file can be created using jar tool found in jdk/bin directory. If you are using Eclipse or Netbeans IDE, you can export your project as a war file.
To create war file from console, you can write following code.
jar -cvf abc.war *  
Now all the files of current directory will be converted into abc.war file.
# 25) What are the annotations used in Servlet 3?
There are mainly 3 annotations used for the servlet.

@WebServlet : for servlet class.
@WebListener : for listener class.
@WebFilter : for filter class.
26) Which event is fired at the time of project deployment and undeployment?
ServletContextEvent.
# 27) Which event is fired at the time of session creation and destroy?
HttpSessionEvent.
# 28) Which event is fired at the time of setting, getting or removing attribute from application scope?
ServletContextAttributeEvent.

# 29) What is the use of welcome-file-list?
It is used to specify the welcome file for the project.
# 30) What is the use of attribute in servlets?
Attribute is a map object that can be used to set, get or remove in request, session or application scope. It is mainly used to share information between one servlet to another.
