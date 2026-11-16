# unity  Scripting 
```
[SerializeField]
```

What is it?

[SerializeField] allows a private variable to be visible and editable in the Unity Inspector.
-----------------------------------------------------------------------
OnTriggerEnter2D

```
void OnTriggerEnter2D(Collider2D collision)
```
 Unity callback method that is automatically called when another Collider2D enters a Trigger Collider2D.
 برای تشخیص ورود آبجکت‌ها به محدوده یکدیگر، بدون اینکه برخورد فیزیکی مانع حرکت آن‌ها شود
 ---------------------------------------------------------------------
 GetComponen

 GetComponent is a Unity method used to access a component attached to a GameObject.
```
GetComponent<Rigidbody2D>();
```
متدیست که برای دسترسی  به یک کامپوننت روی یک گیم ابجکت.
-----------------------------------------------------------
```
bool
```

bool – Used when we need to check or store a state with only two possible values: true or false.
```
bool=true
bool=false
```
____________________________________
Destroy 
```
Destroy(collision.gameObject);
```
Destroys (removes) the GameObject that collided with another object
----
آبجکتی را که با آبجکت دیگری برخورد کرده است، از صحنه بازی حذف می‌کند .محدود به متد خاصی نیست؛ هرجا نیاز به حذف آبجکت داشته باشیم می‌توانیم از آن استفاده کنیم
______________________________________________



