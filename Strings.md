### Important Points to Note:
###### String is a Final class; i.e once created the value cannot be altered.
Thus String objects are called immutable.
###### The Java Virtual Machine(JVM) creates a memory location especially for Strings called String Constant Pool.
That’s why String can be initialized without ‘new’ keyword.
###### String class falls under java.lang.String hierarchy.
But there is no need to import this class.
Java platform provides them automatically.
String reference can be overridden but that does not delete the content; i.e., if
String h1 = "hello";

h1 = "hello"+"world";

then "hello" String does not get deleted. It just loses its handle.

###### Multiple references can be used for same String but it will occur in the same place; 
i.e., if
String h1 = "hello";

String h2 = "hello";

String h3 = "hello";

then only one pool for String “hello” is created in the memory with 3 references-h1,h2,h3

If a number is quoted in “ ” then it becomes a string, not a number anymore. That means if
String S1 ="The number is: "+ "123"+"456";

System.out.println(S1);

then it will print: The number is: 123456

If the initialization is like this:

String S1 = "The number is: "+(123+456);

System.out.println(S1);
