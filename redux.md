# Redux

Redux is a solution to a common problem that can be applied in any framework, react this case; redux is responsible of managing the global state, storing and distributing to the components that require it, no matter how far apart they are (in terms of nodes or levels) from each other.

**Store concept:**
The only source of truth and storage for our data in Redux is called a store. Something very important about the Store is that according to the data flow it is easy to read data from there, but writing it is a very different story.


to change the state we must use a combination of different **actions** that describe the reason for what we want to change, and additionally a set of **reducers** that will be in charge of determining what the final state is given the actions


<center>

![Redux Pattern](/assets/redux.png)

</center>

As can be seen in the image, the flow only goes in one direction, hence the reason why reading the state is easier than changing it, and despite the fact that more elements are missing to be able to manage the state, the idea of its status can be abstracted. operation: a store where the global state of the application is located and from where any component, no matter where it is, can access that information.


<a href="https://github.com/carlosHGit/redux-counter">Redux-counter project</a>

