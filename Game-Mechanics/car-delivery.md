 1:  #فقط بسته ای که تحویل گرفته قبلا بتواند تحویل، و یادش بمونه بسته داره.
```
if (collision.CompareTag("Package") && !hasPackage)
{
hasPackage = true;
GetComponent<ParticleSystem>().Play();
Destroy(collision.gameObject, delay);
}
```
```CompareTag("Package")```
تشخیص اینکه با چه چیزی برخورد کردیم. هر برخوردی بسته نیست,ممکن است دیوار یا مشتری باشد.


