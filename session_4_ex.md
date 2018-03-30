# Session 4

The following exercise will have to be pushed to your personal account
in https://home.tuxlinuxien.com:9999/

## requirements

Your folder should be called **session_4_ex** and MUST be **private**. Any
public repository will be removed without notice. No need to tell you the score
that goes with it.

Your path will look like https://home.tuxlinuxien.com:9999/ **student id** /session_4_ex

Add a file called `.gitignore` at the root of your repository to make sure you
don't push unwanted files.

## files

* infint.cpp
* infint.hpp
* .gitignore

## exercise

The goal of this exercise is to build an infinite calculator. As you know (or
not), each type of number that your are using has a limited space in memory.
With the 64 bits architecture you can store pretty huge numbers.

```
For example:

Int32
32-bit signed integer
Min/Max Value: -2,147,483,648 / 2,147,483,648

Int64
64-bit signed integer
Min/Max Value: -9,223,372,036,854,775,808 / 9,223,372,036,854,775,808
```

Now, what if we need to store a number bigger that this? We can consider using
a `long` or `long long` but again, what if we want to store a number bigger
than a `long long`?

We will create a new type of *number* than is no more limited by it size.

Consider now the following program:

```c++
// main.cpp

#include <iostream>
#include "infint.hpp"

int main() {
    Infint num = Infint();
    // or Infint num = Infint(0);


    num = num + 1;  // num is equal to "1"
    num += 1;       // num is equal to "2"
    num *= 5;       // num is equal to "10"
    num -= "5";     // num is equal to "5"
    num -= num;     // num is equal to "0"


    num = 1;                // num is equal to "1"
    num++;                  // num is equal to "2"
    num = num + num + 1;    // num is equal to "5"
    num--;                  // num is equal to "4"

    std::cout << num << std::endl;
    return 0;
}
```

Once compiled and executed:

```
$> ./a.out
$> 4
```

Our number will have to be stored into a `string`. If we try to store it into
any integer type it will work at the beginning  but if we try to insert a number
with 2000 digits (ex: 12345[lot of more here]32432432 ) then we will have an
overflow.


We will provide 3 constructor:

* `Infint::Infint()` where the default value is "0"
* `Infint::Infint(int)`
* `Infint::Infint(std::string)`

To make it a bit easier, we will only support integers with the following
operators 

* `+`
* `-`
* `++`
* `--`
* `+=` 
* `-=` 
* `=` 

Our `Infint` will be included in the `0 <= Infint <= +inf`.

## warnings

* only the listed file above should be in the repository. If any other file is
added your score will automatically be 0/100.
* break the server then I will break your fingers.

## tips

* read this whole document a second time.
* read this whole document a third time.
* baidu is your friend during your homework, I am not. Asking for help while
you could have got the solution on baidu will **cost** you points.
