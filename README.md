# DesignPatternByExample
Identifying various GOF patterns in existing projects

Dot Net Framework and Java Core Libraries have used lot of GOF pattern used at multiple places. Some of [StackOverflow.com](https://stackoverflow.com/questions/1673841/examples-of-gof-design-patterns-in-javas-core-libraries) [answer list](https://stackoverflow.com/questions/1316743/are-there-any-design-patterns-used-in-the-net-framework) few places where these patterns are used in these farameworks. This blog post contains some of my own finding of GOF Patterns in these libraries.

## Decorator Design Pattern
### Key Idea 
Decorator Pattern lets you add extensions to functionality to an object after construction time.

	1. Used by Microsoft Dotnet Presentation Framework in creating various [decorator classes](https://referencesource.microsoft.com/#PresentationFramework.Luna/Microsoft/Windows/Themes/ButtonChrome.cs,153)

	2. InputStream is an abstract class.Most concrete implementations like BufferedInputStream, GzipInputStream, ObjectInputStream, etc. have a constructor that takes an instance of [the sameabstract class.](https://docs.oracle.com/javase/8/docs/api/java/io/InputStream.html)
	Or in .net  like BufferedStream, CryptoStream, GzipStream, etc. All those decorate Stream class.
	
	
## Proxy Design Pattern
### Key Idea
A proxy is a wrapper or agent object that is being called by the client to access the real serving object behind the scenes. In the proxy, extra functionality can be provided, for example caching when operations on the real object are resource intensive.A protection proxy might be used to control access to a resource based on access rights.

	1. WCF Proxy - https://docs.microsoft.com/en-us/dotnet/framework/wcf/accessing-services-using-a-wcf-client
  2. Microsoft Graph SDK - https://github.com/microsoftgraph/msgraph-sdk-dotnet
  
## Flyweight DesignPattern
### Key Idea
When these objects are immutable, i.e. they do not modify its internal state except maybe for reattaching to a new set of state data, and some additional conditions are met. We can Use flyweight pattern.
 1. [String Intern](https://stackoverflow.com/questions/2909848/how-does-java-implement-flyweight-pattern-for-string-under-the-hood)
	2. Word processor
	3. Boost Flyweight library, lets you create new Flyweight object easily(https://www.boost.org/doc/libs/1_62_0/libs/flyweight/doc/tutorial/basics.html)
 Implementionaton  https://www.boost.org/doc/libs/1_62_0/boost/flyweight/serialize.hpp
 
 
## Flyweight DesignPattern
### Key Idea
 Methods taking an instance of different abstract/interface type and returning an implementation of own abstract/interface type which delegates/uses the given instance
  1. [tlbimp.exe](https://docs.microsoft.com/en-us/dotnet/framework/tools/tlbimp-exe-type-library-importer)
  2. [StreamReader](https://referencesource.microsoft.com/#mscorlib/system/io/streamreader.cs,925a52135ca31cfa)
  
##Bridge Design Pattern
### Key Idea
The Bridge pattern is an application of the old advice, "prefer composition over inheritance".


##Composite Design Pattern
TreeView Class which is of Type ItemControl can addChild with a type of ['ItemCOntrol'] (https://msdn.microsoft.com/en-us/library/system.windows.controls.treeviewitem(v=vs.110).aspx)

Other References
1.[RigsOfRods Case Study](http://codergears.com/Blog/?p=720)
2. [JBoss](https://www.codeproject.com/Articles/486288/Learn-design-patterns-from-real-projects-JBoss-cas)
3. [More StackOverflow answers](https://stackoverflow.com/questions/6733557/sample-projects-with-design-pattern-statistics)
4. [Behavioural Pattern in Dot Net Framework](http://www.jot.fm/issues/issue_2006_11/article1.pdf)