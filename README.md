# what is this?

Ever tried to run legacy java code (pre java 8) on java 11 and above, that would crash with the following exception?

    java.lang.ClassNotFoundException: javax.xml.bind.DatatypeConverter

Before Java 8 there was no official support for base64 encoding in standard library. Thus, many developers resorted to using not-so-standard classes from JEE that just so happened to be included in the JDK at the time. Among many, it was common to use `javax.xml.bind.DatatypeConverter` just for it's base64 encoding/decoding capabilities.

This class and it's module was part of JakartaEE and has been removed from JDK in Java 11. In Jakarta 3.0 the "javax" part has been changed to "jakarta". (you need Jakarta 2.3 if you want a drop-in replacement)

Chances are (and those changes are huge), that the legacy program you're trying to run uses DatatypeConverter in the manner mentioned above (This often applies to old JavaSE standalone programs) - and if that's the case, this simple drop-in replacement should be enough. 

### how to use it?

Just add it to classpath or merge it with your legacy jar.