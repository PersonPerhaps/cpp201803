# Session 6

All the following exercises will have to be pushed to your personal account
in https://home.tuxlinuxien.com:9999/

## requirements

Your folder should be called **session_6_ex** and MUST be **private**. Any
public repository will be removed without notice. No need to tell you the score
that goes with it.

Your path will look like
https://home.tuxlinuxien.com:9999/ **student id** /session_6_ex

Add a file called `.gitignore` at the root of your repository to make sure you
don't push unwanted files.

## required files

* weapon.cpp
* weapon.hpp
* vehicle.cpp
* vehicle.hpp
* soldier.cpp
* soldier.hpp
* gun.cpp
* gun.hpp
* riffle.cpp
* riffle.hpp
* shotgun.cpp
* shotgun.hpp
* jeep.cpp
* jeep.hpp
* blackbird.cpp
* blackbird.hpp
* sniper.cpp
* sniper.hpp
* infantry.cpp
* infantry.hpp
* captain_america.cpp
* captain_america.hpp

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

* `public virtual int Weapon::countAmmunition() = 0` which will return the
    number of ammunition available
* `public virtual void Weapon::fire() = 0` will print
`BANG with my <weapon_name>\n` and reduce the number of ammunition by -1.
If ammunition is equal to **0** then display `\n` only.
* `public virtual string Weapon::model() = 0` which will return the name
of your weapon

#### attributes

None

### Vehicle

#### methods

* `public int Vehicle::countSoldier() = 0` returns the number of soldier
in the vehicle.
* `public virtual void Vehicle::do() = 0`
* `public void Vehicle::addSoldier(Soldier *)` add a soldier to our vehicule.
* `public std::vector<Soldier*> Vehicle::unload()` will return a `vector` of
soldiers and set the number of soldiers back to **0**

#### attributes

* `private std::vector<Soldier*>`

### Soldier

#### methods

* `public void Soldier::scream()` will print `AAAAHHH\n`
* `public virtual void Soldier::identification()` will print
`<rank> <solider_name> Sir!\n`
* `public virtual void Soldier::fireLeft()` will `Weapon::fire()` left weapon.
If no weapon is set, then do nothing.
* `public virtual void Soldier::fireRight()` will `Weapon::fire()` right
weapon. If no weapon is set, then do nothing.
* `public virtual void Soldier::setRight(Weapon *)`
* `public virtual void Soldier::setLeft(Weapon *)`

#### attributes

* `private Weapon* left`
* `private Weapon* right`
* `private string name`
* `private string rank`


Since the described classes all have at least one pure virtual method, we can't
instantiate them directly without have a g++ error.

## Gun

The `Gun` class will inherit from a `Weapon` class, it will have at least

* `protected int ammunition`
* `protected string name`
* `public Gun(string name, int ammo)`

## Riffle

The `Riffle` class will inherit from a `Gun`. The constructor will have to be
like `Riffle::Riffle()` and set the name to **riffle** and the ammo count to
**10** automatically.

**This class will only contain a constructor**

## ShotGun

The `ShotGun` class will inherit from a `Gun`. The constructor will have to be
like `ShotGun::ShotGun()` and set the name to **shot_gun** and the ammo count
to **5** automatically.

**This class will only contain a constructor**

## Jeep

The `Jeep` class will inherit from a `Vehicle`. The constructor will have to be
`Jeep::Jeep()`.

We will have to implement the method `do()` which will print
`Fast and Furious sucks\n`

## BlackBird

The `BlackBird` class will inherit from a `Vehicle`. The constructor will have
to be like `BlackBird::BlackBird()`.

We will have to implement the method `do()` which will print
`On my way guys! OVER\n`

## Sniper

The `Sniper` class will inherit from a `Soldier`. The constructor will have to
be `Sniper::Sniper(string name)`. The default rank will be `sniper`.

## Infantry

The `Infantry` class will inherit from a `Soldier`. The constructor will have
to be `Infantry::Infantry(string name)`. The default rank will be `sergeant`.

## CaptainAmerica

The `CaptainAmerica` class will inherit from a `Soldier`. The constructor will
have to be `CaptainAmerica::CaptainAmerica()`.

`identification()` will print `I am Captain America but I wish I was Batman.\n`

`setLeft(Weapon *)` and `setRight(Weapon *)` will only print
`I don't need it, I have my vibranium shield.`

`fireLeft()` and `fireRight()` will only print `PLEASE HELP ME SpiderMan!!!\n`
even he has weapons attached to his hands or not.
