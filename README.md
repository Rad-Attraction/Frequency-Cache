# Frequency-Cache

##Save python dicts as json files while caching the most frequent items in memory.

Just storing data in a dictionary object, 
we can save and load as json easily when the program wakes and shuts down.
But as our dictionary increases in number of items, 
then the ram the program needs increases as well.

This class saves the data as json, reads it when needed,
and keeps a certain number (100 by default) of items in memory.
It keeps track of how often each item is accessed,
and when more items are read from json than the maximum size, 
the least frequently accessed item is decached and saved to file.


### Problems

i havent quite tested it against the naive solution of 
just keeping shit in ram lol. 
for all i know this could just be pure overhead.

To test this i would want to generate a series of dummy databases
of varying sizes, and varying distributions of access frequencies
and then i might get a clue as to the sizes for which 
this class is better than just keeping the whole thing in ram.
    
	
Keys are used directly as OS filenames, 
so this has the potential to break since a key might be an invalit os filename.

This might be fixed by hashing filenames into alphanumeric hashes, but then i have to worry about collision and also special names like con.
there might be some library for os strings for python somewhere.