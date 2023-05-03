### `CharArrayList()`

**Implementation:**
make empty array list
set data variables to zero 
create array and create 0 size array

**Errors:**
does constructor fail
Assert
	are all data variables actually 0


### `CharArrayList(char c)`

**Implementation:**
make the arraylist of size 1
set data variables to 1 and capacity to 2 * size + 2
create array and create 1 size array

**Errors:**
Does constructor fail
	test with input
	Invariant: not a char
Assert
	Array size is not 1
	capacity is wrong

### `CharArrayList(char arr[], int size)`

**Implementation:**
make the arraylist of size 
set data variables to parameter and capacity to size
create array and create size array

**Errors:**
Does constructor fail
Assert
	Array size is not 1
	capacity is wrong

### `CharArrayList(const CharArrayList &other)`

**Implementation:**
iterate through data array and copy each value at each index
copy all other data variables correctly

**Errors:**
Does constructor fail
Assert
	Array size is not size of previous array
	Data is generally not the same as the old object

### `~CharArrayList()`

**Implementation:**
delete array

**Errors:**
Does destructor fail
	valgrind


### `CharArrayList &operator=(const CharArrayList &other)`

**Implementation:**
delete current array
set data types to 0

deep copy (see copy constructor)

**Errors:**
Valgrind, is all memory recycled

### `bool isEmpty()`

**Implementation:**
reflect if size is 0 or not

**Errors:**
Assert
	size 0

### `void clear()`

**Implementation:**
recycle array
create a new one of size 0


**Errors:**
assert `isEmpty()`
==In conjunction with to string to check empty==

### `int size() const`

**Implementation:**
return size

**Errors:**

Attempt to throw

Make a dummy list
Check its size with a literal

### `char first() const`
**Implementation:**
throw error if there is an empty array
runtime_error: `cannot get first of empty ArrayList`
return the first element

**Errors:**

Attempt to throw

Make a dummy list
Check its first with a literal

### `char last() const`
**Implementation:**
throw error if there is an empty array
runtime_error: `cannot get last of empty ArrayList`
return the last element

**Errors:**

Attempt to throw

Make a dummy list
Check its last with a literal

### `char elementAt(int index) const`
**Implementation:**
throw error if index is not in range
range_error: `index (IDX) not in range [0..SIZE)`

**Errors:**

Attempt to throw
==what happens if empty==
	no number exists in `[0,0)`, see piazza
	
Make a dummy list
Check its index element with a literal

### `std::string toString() const`

**Implementation:**
use an sstream like in lab

`[CharArrayList of size 5 <<Alice>>]`

**Error:**
Make a dummy list
Check its output with a literal


### `std::string toReverseString() const`

**Implementation:**
use an sstream like in lab
same as `toString()` just reverse for loop

`[CharArrayList of size 5 <<Alice>>]`

**Error:**
Make a dummy list
Check its output with a literal


### `void pushAtBack(char c)`

**Implementation:**
if size == capacity
	expand

Assign `char c` at `size` index
increment size

**Error:**
Make a dummy list
Check its output with a literal

### `void pushAtFront(char c)`

**Implementation:**
if size == capacity
	expand

| 0 | 1 | 2 | 3 | 4 |
|--|--|--|--|--|
make a temp array of size+1
assign the `char c ` to the the new array[0]
assign each value of the array to the new array[i+1]
delete old array
old array points to new array now


increment size

==check naming in style guides here==

### `void insertAt(char c, int index)`

**Implementation:**
throw error if index is not in range
range_error: `index (IDX) not in range [0..SIZE]`

create new array of size+1

if the index is the size 
	assign the each value of the array to the new array`[i]`
	add the `char c`

copy elements from index to size-1 at `[i+1]`
	insert `char c` at index
	copy elements at `[0,index)`

delete old array
old array points to new array now

increment size

**Error:**
Make a dummy list
Check its output with a literal

==ERROR is not printing right==
 

### `void insertInOrder(char c)`

**Implementation:**
while the `char c` is still greater than the current char
	keep on moving
	store index
	break when it is not

call insert method at saved index

**Error:**

Attempt to throw

Make a dummy list
Check its output with a literal

### `void popFromFront()`

**Implementation:**
throw error if there is an empty array
runtime_error: `cannot pop from empty ArrayList`

go from 0 to size - 1
and copy `data[i] = data[i+1]`

decrement size

**Errors:**

Attempt to throw ==catch==


Make a dummy list
Check its output with a literal

### `void popFromBack()`

**Implementation:**
throw error if there is an empty array
runtime_error: `cannot pop from empty ArrayList

make a new array of `size - 1`
copy everything from old array to the new array until size - 1
delete old array
set old array to point to new array

**Errors:**

Attempt to throw

Make a dummy list
Check its output with a literal

### `void removeAt(int index)`
**Implementation:**
throw error if index is not in range
range_error: `index (IDX) not in range [0..SIZE)


create new array of size-1

copy elements from index to size-1 at `[i-1]`
copy elements at `[0,index)`

delete old array
old array points to new array now

decrement size

### `void replaceAt(char c, int index)`
**Implementation:**
throw error if index is not in range
range_error: `index (IDX) not in range [0..SIZE)

`data[index] = c`

**Errors:**

Attempt to throw

Make a dummy list
Check its output with a literal

### `concatenate(CharArrayList *other)`
**Implementation:**
get the sum of both sizes
make an array of that number

fill the array with the first array then the second array

**Errors:**

Make two dummy lists
Check its output with a literal

### `shrink()`
**Implementation:**
if capacity is greater than size
delete the data elements from size to capacity index
**Errors:**

Just check idk get to it later maybe check Piazza????






==YOU HAVE REACHED THE END==


Tests on all constructors

Maybe do more tests combining methods defined later in order originally
E.g. checking `toString()` on constructors
	  erase/clear on `isEmpty()`
	  


Follow last function testing format for throwing help

Do tests where a lot of things are added at once


catch all throws from before in the `unit_test.h`


empty
single
multi
copy
assignment

single time
multiple times


only tested copy  and assignment to make sure that the right things were being clear etc 

went back and added toString to everything to make extra sure that everything was copying correclty

TODO: 
- [x] new tester functions
- [x] new tester functions based on copy, assignment constructors ==make list==
- [x] function contracts
- [ ] in-line comments
- [ ] readme










