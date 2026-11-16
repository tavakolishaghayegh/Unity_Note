Keyboard Input is used to detect keyboard keys pressed by the player to control game objects.
-----
 لایبری موردی استفاده
 ```
using UnityEngine.InputSystem;
```
-----

```
Keyboard.current.wKey.isPressed
```
# example :
```
if (Keyboard.current.wKey.isPressed)
{
    move = 1f;
}
```
```
if (Keyboard.current.wKey.isPressed)
{
    move = 1f;
}
else if (Keyboard.current.sKey.isPressed)
{
    move = -1f;
}
```
Keyboard.current دسترسی به کیبورد
--
wKey: ماشین به جلو حرکت می‌کند
--
sKey=ماشین به عقب حرکت می‌کندچون حرکت منفی یک هستش

---
isPressed: بررسی می‌کند که کلید همچنان فشرده و نگه داشته شده است یا خیر.
____________________________________________________________________

