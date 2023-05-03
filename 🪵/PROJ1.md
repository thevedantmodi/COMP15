```c++

//Unit_test for train dummy

// // Tests if Train constructor runs properly

// void train_test_dummy() {

// Train greenLine;

// }

```


There was an issue where I passed the station vector as a value, not by reference. Once the add passenger was done I diffed it with the reference to make sure that they were added properly to the right station PQ

I also made a heap allocated passenger, so I needed to clear the memory so I tried to do that in the Station deconstructor

But I found that it was better to make a struct of stations within MetroSim, as MetroSim was not doing much right now, and could have done more, to cut down on the number of classes in the program.

So I integrated the new Station struct method, and encountered a segfault of an outdated constructor line in the MetroSim constructor, which I narrowed down through cerr statements, even though valgrind was unsure. I also found in this that there was no main.o rule in the Makefile, so there was a linker error when I referenced a MetroSim object. I simply added the rule, and it worked.

The line dealing with the segfault was initialising the train at the first stop, but the stations vector was not added to yet, so I simply added the line to another function that is called after the stations vector is updated with all the stations.

Considering that the add passenger method was tested based on this, because there is no need to test for invariant output according to the spec. 

I wanted to now move on to the metroMove function, which I broke into parts—increasing the station, with accounting for the overlap. Then, check if there are passengers who want to get on at the new station. Then, check if there are passengers who need to get off, print their info, and delete them.

While attempting to increase the station, I found that the Train class was redundant, as there was only one train so it's actions could just be handled by the MetroSim class. This was motivated by the fact that I ended up having to create redundant methods within MetroSim that solely get the data variables of Train. 


```

void Station::print(std::ostream &output) {

platform(output);

output << "[" << ID << "]";

output << " " << name << " {";

queue.print(output);

output << "}" << std::endl;

}

void Station::platform(std::ostream &output) {

if (trainHere) {

output << "TRAIN: ";

} else {

output << " ";

}

}


```


26 lines of m m
1 line of m f

This is because a vector represents an easily resizable list, unlike arrays in C++ so because the amount of passengers and stations are not fixed when they are first created, it makes sense to use a vector. An array is more useful for lists, where the order is fixed upon their creation, such as the amount of cars in the train in MetroSim. 