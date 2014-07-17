FIO_Java
========

This is the File input output class I use for java.

The hasMoreData() is a little bit jenky. I need to fix it. This will manifest itself as a nullpointerexception. 
I think I may have fixed it, but I haven't had an opportunity to run it.

All you do is create a new object in your main class.

  FIO f = new FIO(args[0]);

This is how I use it now, and then I will pass the program the file I want it to open:

  java _Main.class input.txt

For example.
