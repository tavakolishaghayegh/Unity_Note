# Example :
ReadValue<Vector2>() is used to read the player’s input and return it as a 2D vector.  
این دستور ورودی بازیکن را به شکل یک بردار دوبعدی دریافت می‌کند.  
A Vector2 contains two values:

 ● X: Horizontal input (Left / Right).  
 
 ● Y: Vertical input (Up / Down). 
 ```
moveVector = moveAction.ReadValue<Vector2>();
```
nput Values / مقادیر ورودی:  

Input X Y. 

 ● Left / چپ -1 0
 ● Right / راست 1 0
 ● Up / بالا 0 1
 ● Down / پایین 0 -1
 ● No Input / بدون ورودی 0 0
