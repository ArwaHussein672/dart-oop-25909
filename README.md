# Dart OOP Assignment: Kigali Bus Card

**Name:** Arwa Hussein Elrayah Osman
**Student ID:** 25909

## My numbers
- D = 09, L = 9
- Starting balance = 1090 RWF
- Bus fare = 209 RWF
- Student discount = 19%

## Output of main.dart
Error: name too short
Owner: Arwa | Balance: 1090 RWF
Owner: Arwa Hussein Elrayah Osman | Balance: 1090 RWF
Error: top-up must be 500 to 50000 RWF
Topped up 2000 RWF
Paid 209 RWF
Paid 209 RWF
Owner: Arwa Hussein Elrayah Osman | Balance: 2672 RWF

--- Testing StudentCard ---
Owner: Arwa Hussein Elrayah Osman | Balance: 1090 RWF
Student card: 19% off
Student discount: 39 RWF
Paid 170 RWF
Owner: Arwa Hussein Elrayah Osman | Balance: 920 RWF
Student card: 19% off

## Part 1: Why no setter for balance?
It is a good idea because the balance should only be changed through logical operations like `topUp` and `pay`. If there was a setter, anyone could change the balance to any random number (like a million) without actually paying. A bus card balance must only change through allowed actions.

## Part 2: What does ~/ do?
The `~/` operator divides two numbers and returns an integer (it discards the decimal part). 
- `print(237 * 17 / 100);` returns 40.29 (a double).
- `print(237 * 17 ~/ 100);` returns 40 (an int).

## Part 4: Bug table
| Bug | The line | Why it is wrong (your words) | Your fix |
| :--- | :--- | :--- | :--- |
| 1 | `String _brand;` and `int _battery;` | Variables must be initialized in Dart. | Added starting values: `= ''` and `= 0`. |
| 2 | `SmartPhone(String brand, int battery, String system) {` | The child constructor doesn't call the parent constructor. | Added `: super(brand, battery)`. |
| 3 | `@override void restart()` in SmartPhone | The parent `Phone` class has no `restart()` method. | Added `void restart()` to the parent `Phone` class. |
| 4 | `p.battery = 100;` in main | The `battery` field only has a getter, no setter. | Added a setter `set battery(int value)` that accepts 0 to 100. |
| 5 | `print(p.battery());` | `battery` is a getter, not a method. | Removed the parentheses: `print(p.battery);` |
| Not a bug | `int get battery {` | It looks like a method, but it's the correct syntax for a getter. | (none) |

## Part 5
**My prediction:**
- The first number printed is 1.
- The second number printed is 5.

**Why?**
For the first Bag (a): We started at 0, then `a.add()` made it 1. Then `a.items = -5` was refused because of the rule `if (value >= 0)`, so it stayed 1.
For the BigBag (b): We started at 0. The BigBag calls `super.add()` twice, so every `b.add()` adds 2 items. We called it twice, so 0 + 2 + 2 = 4. Then `b.items = b.items + 1` made it 5.

**Real output:**
1
5

**Was I right?** Yes, my prediction was correct!