# 1
بازیکن فقط وقتی بتواند بسته را تحویل بدهد که قبﻼ ً آن را برداشته باشد. برای همین باید بازی
«یادش بماند» بازیکن بسته دارد یا نه
```
hasPackage
```
 
# 2
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


