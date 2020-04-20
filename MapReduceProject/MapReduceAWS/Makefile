compileJava:
	#hadoop com.sun.tools.javac.Main <javacode>
	hadoop com.sun.tools.javac.Main AnalyzeRedditData.java

JarJava: compileJava
	# jar cf <nameofjar> <classfiles>
	jar cf ard.jar AnalyzeRedditData*class

startMapReduceSMALL: compileJava JarJava
	# hadoop jar <jarname> <className> <inputs> <output>
	hadoop jar ard.jar AnalyzeRedditData "./Reddit Data/data-small" "./Reddit Data/small-output"

startMapReduceLARGE: compileJava JarJava
	hadoop jar ard.jar AnalyzeRedditData "./Reddit Data/data-large" "./Reddit Data/large-output"

clean:
	rm ./*.class
	rm -rf "./Reddit Data/small-output"
	rm -rf "./Reddit Data/large-output"
	rm -rf ard.jar
