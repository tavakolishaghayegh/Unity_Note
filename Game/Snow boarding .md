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
# To Restart Level
Script :finishline , CrashDetector
```
[SerializeField] float restartDelay=1f;
[SerializeField] ParticleSystem finishParticles;
void OnTriggerEnter2D(Collider2D collision) {
 int layerIndex = LayerMask.NameToLayer("player");
if(collision.gameObject.layer == layerIndex)
    {
      finishParticles.Play();
      Invoke("ReloadScene" ,restartDelay );

      
    }
}
void ReloadScene()
  {
    SceneManager.LoadScene(0);
  }
}
```
_____________________________________
# invoke ()
Creating A Delay
```
Invoke("MethodName", delay);
```
اجرای یک متد با تأخیر مشخص.  
________________________________________
# SceneManager.LoadScene()
بارگذاری مجدد صحنه.  
```
void ReloadScene()
{
    SceneManager.LoadScene(0);
}
```
___________________________________________
# Particle System Reference
```
[SerializeField] ParticleSystem finishParticles;
{
if(){ 
  finishParticles.Play();
 }
}
```
این دستور افکت ذرات اختصاص‌داده‌شده را اجرا می‌کند
_________________________________________
```
void OnTriggerEnter2D(Collider2D collision) {
    
    int layerIndex=LayerMask.NameToLayer("Floor");

    if (collision.gameObject.layer == layerIndex)
    {
      playercontolloer.DisableControls();
      crashParticles.Play();
     Invoke("ReloadScene",restartDelay);
    }
    
  }
  void ReloadScene()
  {
    
    SceneManager.LoadScene(0);
  }

}
```
int layerIndex=LayerMask.NameToLayer("Floor");Gets the layer index of the Floor layer.  
playercontolloer.DisableControls();کنترل‌های بازیکن را غیرفعال می‌کند تا بعد از برخورد نتواند همچنان حرکت کند یا بچرخد
__________________________________________________________________
# DisableControls()
بعد از سقوط، بازیکن دیگه نمی‌تونه با کیبورد شخصیت رو کنترل کنه.
______________________________________________________________________________
# Effect
```
[SerializeField] ParticleSystem finishParticles;
crashParticles.Play();
 finishParticles.Play();
```
________________________________________________
# speed up when use push 
```
[SerializeField] float BoostSpeed=20f;
[SerializeField] float baseSpeed =15f;
SurfaceEffector2D surfaceEffector2D;
 void BoostPlayer()
    {
        
        if(moveVector.y > 0)
        {
            surfaceEffector2D.speed=BoostSpeed;
        }
        else
        {
            surfaceEffector2D.speed=baseSpeed;
        }
    }
```


وقتی بازیکن کلید بالا را فشار می‌دهد، مقدار moveVector.y مثبت می‌شود. 

____________________________________________________________________________
# OnCollisionExit2D
این متد برای پایان تماس فیزیکی استفاده می‌شود.  
```
 [SerializeField] ParticleSystem snowParticles;
void OnCollisionExit2D(Collision2D collision)
{
 int layerIndex=LayerMask.NameToLayer("Floor");
        if (collision.gameObject.layer == layerIndex){
    snowParticles.Stop();
}
}
```
برعکس:
```
 [SerializeField] ParticleSystem snowParticles;
void OnCollisionEnter2D(Collision2D collision)
{
 
            snowParticles.Play();
        }
```
____________________________________________________________









