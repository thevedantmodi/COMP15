
- If making two hases for different case sensitivities if run into memory problems, go troubleshoot that firtsy

# New plan
- Big hash table using `std::hash` to get bucket 
	- Bucket holds `Word`
		- `Word` has string of word and vector of paths 
			- s.t. if new word, make a new item in bucket and location, and if same word, add to paths list
- `% TABLE_SIZE`
	- `1009` because big prime
- Use linear probing for collisions
	- Yes it's more space, but we want faster rather than smaller
- If load factor is over `0.7` expand
	- `TABLE_SIZE = 2 * TABLE_SIZE + 2`


```

/* word.h

  

Header file for Word class

John Cha and Vedant Modi (jcha04 and vmodi01)

  

Stores the name of the word and the locations of the word

*/

  

#include <string>

#include <vector>

  

class Word {

public:

Word();

Word(std::string name);

private:

std::string key;

std::vector<std::string> paths;

};

```

