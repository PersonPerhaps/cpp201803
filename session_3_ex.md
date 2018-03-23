# Session 3

All the following exercises will have to be pushed to your personal account
in https://home.tuxlinuxien.com:9999/

## requirements

Your folder should be called **session_3_ex** and MUST be **private**. Any
public repository will be removed without notice. No need to tell you the score
that goes with it.

Your path will look like https://home.tuxlinuxien.com:9999/&lt;student id&gt;/session_3_ex

Add a file called `.gitignore` at the root of your repository to make sure you 
don't push unwanted files.

## ex 1

in your repository, create a file **main_1.cpp** where you will implement your
first cpp program.

Output:

```
$> ./a.ou
hello world!
$>
```

## ex 2

In a file **student_2.hpp**, you will have to *define* the `Student` class based
on the following cpp file.


```
// student_2.cpp
#include <iostream>
#include "student_2.hpp"

Student::Student(string first_name, string last_name) {
    this->first_name = first_name;
    this->last_name = last_name;
}

Student::showFirstName() {
    std::cout << this->first_name << std::endl;
}

Student::showLastName() {
    std::cout << this->last_name << std::endl;
}

Student::showFullName() {
    std::cout << this->last_name << " " << this->first_name << std::endl;
}
```

*notice*: `student_2.cpp` shouldn't be submitted or the exercise will be
considered as invalid.

## ex 3

In a file **hello_3.cpp**, you will have to *implement* the `Hello` class based
on the following hpp file.

```
// hello_3.cpp
# ifndef __HELLO_HPP_
# define __HELLO_HPP_

class Hello {
public:
    Hello();
    void world();
};

#endif
```

 * `Hello` constructor won't have to do anything
 * `world` will only display `world!` without any carriage return at the end.

## ex 4

Implement a `Car` into files `car_4.cpp` and `car_4.hpp`.

### main test

```
// main.cpp
#include "car_4.hpp"

int main() {
    Car *my_car = new Car(4, "Peugeot", "red");
    my_car->displayWheels();
    my_car->displayBrand();
    my_car->displayColor();

    Car *my_other_car = new Car(4, "jingbei", "BLUE");
    my_other_car->displayWheels();
    my_other_car->displayBrand();
    my_other_car->displayColor();

    return 0;
}
```

Once compiled and run:

```
$> ./a.out
The car has 4 wheels.
This car is from Peugeot.
The Peugeot is RED.
The car has 4 wheels.
This car is from jingbei.
The jingbei is BLUE.
```

notice: `main.cpp` will make your exercise invalid if you push it.

## warnings

* only the listed file above should be in the repository. If any other file is
added your score will automatically be 0/100.
* If any exercise is wrong, then the robot will stop checking the next
exercises. This means that is your first exercise is **wrong** and the others
are correct, then you score will be 0/100.
* break the server then I will break your fingers.

## tips

* read this whole document a second time.
* read this whole document a third time.
* baidu is your friend during your homework, I am not. Asking for help while
you could have got the solution on baidu will **cost** you points.
