# Game Design
Player Experience:
Smooth, relaxing Core Mechanic:
Don't crash
Game Loop:
Reach the end to win.  
____________________________________________________________________________________

# Reusable Scripts:
CharSelectemanager:انتخاب کاراکتر (دینو یا قورباغه) و شروع بازی.  
playercontolloer:کنترل بازیکن: چرخش، بوست، شمارش فلیپ و اعمال پاورآپ.  
CrashDetector:تشخیص برخورد سر با زمین و ری‌استارت.  
finishline:خط پایان و ری‌استارت.  
SnowTrail:پخش ذرات برف هنگام تماس با زمین.  
ScoreManager:نگهداری و نمایش امتیاز.  
PowerupSO:داده‌های پاورآپ.  
powerupManager:جمع کردن پاورآپ و تایمر آن.  
____________________________________________________________________________________
# Surface Effector:
is a Unity component that applies a movement force to objects when they come into contact with a surface.
____________________________________________________________________________________
# Component Reference
```
 Rigidbody2D myRigidbody2D;
void Start()
    {
       
       myRigidbody2D=GetComponent<Rigidbody2D>();
      
    }
```
____________________________________
# torque:
برای ایجاد نیروی چرخشی روی رجید بادی استفاده می‌شو
```
AddTorque(جهت)
```
Player Rotation with Torque:یعنی چرخاندن بازیکن با استفاده از نیروی چرخشی
```
[SerializeField] float torqueAmount=1f;
InputAction moveAction;
Rigidbody2D myRigidbody2D;
Vector2 moveVector;
void RotatePlayer()
    {
        
        moveVector=moveAction.ReadValue<Vector2>();
        if(moveVector.x < 0)
        {
             myRigidbody2D.AddTorque(torqueAmount);
        }
         else if(moveVector.x > 0)
        {
             myRigidbody2D.AddTorque(-torqueAmount);
        }
    }
```
کنترل چرخش بازیکن با استفاده از ورودی کیبورد و نیروی چرخشی.  
InputAction moveAction;ورودی حرکت بازیکن  را در کلید نگه می‌دارد؛.  
Vector2 moveVector;ورودی بازیکن را در قالب یک بردار دوبعدی ایکس و ایگرگ ذخیره می‌کند
_________________________________________________________________________________________________________
