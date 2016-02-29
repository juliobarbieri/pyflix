Python module for accessing Netflix APIs

This module is set up to access the REST resources from the netflix APIs as objects.  There are currently Catalog, User, and Disc objects (as well as a Client object to handle the connections).  You can search for titles or people, and there are methods to retrieve authentication tokens.  The user object can be used to retrieve metadata about the user as well as look at their rental queue.  There are functions for viewing the queues, and adding, deleting, and moving things around.

All the tests pass, and the example code works, and I don't intend to change anything out from under you, so feel free to use this for whatever you like. I can't make reasonable unit tests for the auth stuff, alas, because retrieving a token invalidates your old one.  But I did verify that the token generation cycle in example.py (described in the README file) works correctly.

Before you can play with this you'll need a <a href='http://developer.netflix.com/'>Netflix API Key</a>

Once you have an API Key, you can insert the key and secret into the example.py file and work with it right away.  The example.py code is smart enough to only try to access protected resources if requested via the command line flag -a.

In order to access any of the user-protected resources, follow the instructions in the <a href='http://code.google.com/p/pyflix/source/browse/trunk/README'>README</a> to generate consumer request and access tokens for your use in example.py or test.py.  In the real world you'll want to be generating those consumer tokens for the specific user using the code, but it's very helpful to see what you can do at the different levels of access.

There is a test.py file which works with py.test, but you will need to insert the appropriate key/secrets in this as well to make it work for you.