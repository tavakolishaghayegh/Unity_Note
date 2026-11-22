# Delayed Method Execution
برای اجرای یک متد بعد از گذشت مدت‌زمان مشخص استفاده می‌کنیم

```
Invoke("MethodName", delay);
```
Example :
```
Invoke("PlayEffect", 3f);

void PlayEffect()
{
    particles.Play();
}
```
