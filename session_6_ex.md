# Session 6

All the following exercises will have to be pushed to your personal account
in https://home.tuxlinuxien.com:9999/

## requirements

Your folder should be called **session_6_ex** and MUST be **private**. Any
public repository will be removed without notice. No need to tell you the score
that goes with it.

Your path will look like https://home.tuxlinuxien.com:9999/ **student id** /session_6_ex

Add a file called `.gitignore` at the root of your repository to make sure you
don't push unwanted files.

## The C++ army

For this exercise, we will have to build a code that relies a lot on
polymorphism and inheritance.

Just image you are developing a video game where you can reuse code as much as
possible and the behavior is really predictable.

We will have to build different units for our army which will be divided into
different categories as follow:

* Weapon
* Vehicle
* Soldier

You will use those categories as **class names**

```cpp
// Example
class Weapon {};

class Vehicle {};

class Soldier {};
```

### Weapon

#### methods

* `public virtual int Weapon::countAmmunition() = 0` which will return the number of ammunition available
* `public virtual void Weapon::fire() = 0` will print `BANG with my <weapon_name>\n` and reduce the number of ammunition by -1.
If ammunition is equal to **0** then display `\n` only.
* `public virtual string Weapon::model() = 0` which will return the name of your weapon

#### attributes

None

### Vehicle

#### methods

* `public int Vehicle::countSoldier() = 0` returns the number of soldier
in the vehicle.
* `public virtual void Vehicle::do() = 0` will print `I am <action>\n`
* `public void Vehicle::addSoldier(Soldier *)` which will return the name of your weapon
* `public std::vector<Soldier*> Vehicle::unload()` will return a `vector` of soldiers and set the number
of soldiers back to **0**

#### attributes

* `private std::vector<Soldier*>`

### Soldier

#### methods

* `public void Soldier::scream()` will print `AAAAHHH\n`
* `public void Soldier::identification()` will print `<solider_name>\n`
* `public void Soldier::fireLeft()` will `Weapon::fire()` left weapon. If no weapon is set, then do nothing.
* `public void Soldier::fireRight()` will `Weapon::fire()` right weapon. If no weapon is set, then do nothing.
* `public void Soldier::setRight(Weapon *)`
* `public void Soldier::setLeft(Weapon *)`

#### attributes

* `private Weapon* left`
* `private Weapon* right`
* `private string name`
