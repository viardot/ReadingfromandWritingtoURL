Based on the Oracle java tutorial
https://docs.oracle.com/javase/tutorial/networking/urls/readingWriting.html
  

There are 3 parts in building a servlet that is/will be hosted on a Jetty server.
First part is the Jetty home folder containing the jetty engine. Then there is the
the Jetty base folder. That contains everything needed to publish the servlet. And
last is the development environment where the servlet is build.

download and install the Jetty engine.
1. download the zip file
2. extract the zipfile
   unzip zipfile.zip -d /usr/lib

create the deployment part.
1. create a jetty base directory
2. $ cd jetty_base
   $ jetty_base: java -jar jetty-home-10.0.5/start.jar --add-modules=deploy,http

compile the project
1. $ src: javac -cp outDir/WEB-INF/lib/javax.servlet-api-3.0.1.jar servlet.java -d outDir/WEB-INF/classes/
2. $ src: cd outDir
3. $ src/outDir: jar -cvf reverseservlet.war *
4. $ src/outDir: mv reverseservlet.war ../../jetty_base/webapps*

start the server with:
$ jetty_base: java -jar jetty-home-10.0.5/start.jar

Run the applicatiom
$ src: localhost:8080/reverseservlet/reverse "hello world"
dlrow olleh

*in the code example src/outDir are subdirectories of jetty_base
