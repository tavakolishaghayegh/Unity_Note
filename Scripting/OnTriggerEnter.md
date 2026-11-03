Example of delivery-car game:
ماشین از روی بسته عبور می‌کنه، بسته شناسایی می‌شه و از صحنه حذف می‌شه؛ بدون اینکه جلوی حرکت ماشین رو بگیره
```
void OnTriggerEnter2D(Collider2D collision)
{
    if (collision.CompareTag("Package"))
    {
        Destroy(collision.gameObject);
    }
}
```
