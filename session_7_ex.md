# Session 7

All the following exercises will have to be pushed to your personal account
in https://home.tuxlinuxien.com:9999/

## requirements

Your folder should be called **session_7_ex** and MUST be **private**. Any
public repository will be removed without notice. No need to tell you the score
that goes with it.

Your path will look like
https://home.tuxlinuxien.com:9999/ **student id** /session_7_ex

Add a file called `.gitignore` at the root of your repository to make sure you
don't push unwanted files.

## required files

* my_list.hpp
* my_list.cpp

## My list

For this exercise, we will **kinda** re-implement the **std::list<T>** type and
make it a bit powerful, and since you are familiar with operator overload, we
will combine them to this exercise too.

Here is the list of methods that you will have to implement:

```c++
// my_list.hpp

template<class T> class MyList {
private:
    T* items; // an array of items.
public:
    MyList();
    ~MyList();
    operator+=(T&); // Adds a new item at the end.
    operator+(T&); // Adds a new item at the beginning.
    operator+(MyList<T> l&); // append the content of "l" at the end of your list.
    operator=(MyList<T> l&); // copy the list "l" into your list and removes the existing items.
    T& operator[](int)  // returns an item located at a desired position.
    T front();     // Returns a copy of the first element in the list
    T back();       // Returns a copy of the last element in the list
    push_front(T& g);    // Adds a new element ‘g’ at the beginning of the list
    push_back(T& g);     // Adds a new element ‘g’ at the end of the list
    T pop_front();    // Removes the first element of the list, and reduces size of the list by 1
    T pop_back();     // Removes the last element of the list, and reduces size of the list by 1
    T* begin();     // Returns a pointer of the first element of the list
    T* end();       // Returns a pointer of the last element of the list
    bool empty();   // Returns whether the list is empty(1) or not(0)
    insert(int pos, T&);  // Inserts new elements in the list before the element at a specified position
    erase(int pos);   // Removes a single element at a position
    reverse();            // Reverses the list
    size_t size();  //Returns the number of elements in the list

};
```

## info

You will have to make sure that you don't have any memory leak. Any allocated
memory should be freed. ALWAYS.

## warnings

* only the listed file above should be in the repository.
* break the server then I will break your fingers.

## tips

* read this whole document a second time.
* read this whole document a third time.
* baidu is your friend during your homework, I am not. Asking for help while
you could have got the solution on baidu will **cost** you points.

## cheat

**I gave you a second chance if you cheated last time. This
time if you get caught, the score of this exercise AND the score of all your
previous exercises will be divided by 2**

I will consider you have cheated if:

* you have copied partially/entirely code from another student
* if you have copied code from std::list
* if you are using std::list,std::vector,etc...
