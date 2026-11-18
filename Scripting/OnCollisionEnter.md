# OnCollisionEnter()
• Used to detect when two GameObjects physically collide in a 2D game. 
```
void OnCollisionEnter2D(Collision2D collision)
{
    // Code runs when a collision occurs
}
```

# کاربردها:  
• برخورد ماشین با دیوار.   

• برخورد بازیکن با دشمن.  

• برخورد آبجکت با زمین.  

• تشخیص برخورد برای وارد کردن آسیب.  
Example :
```
void OnCollisionEnter2D(Collision2D collision)
{
    if (collision.gameObject.CompareTag("Wall"))
    {
        Debug.Log("Car hit the wall!");
    }
}
```
• Collision2D collision: اطلاعات مربوط به آبجکت برخوردکننده را دریافت می‌کند.    
is Trigger=off.


