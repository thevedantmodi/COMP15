Check at end of while loop that current node is a leaf (it better be the case)

```c++
while (not curr->isLeaf()) {

cerr << "C: " << c << "\n";

	if (c == '0') {
		curr = curr->get_left();
		bits.get(c);
	} else if (c == '1') {
		curr = curr->get_right();
		bits.get(c);
	  }
	}
```