When the car touches a package:

* CompareTag("Package"): Checks if the object is a package.
* !hasPackage: Prevents picking up multiple packages.
* hasPackage = true: Updates the game state.
* ParticleSystem.Play(): Plays a visual effect.
* Destroy(): Removes the package after a delay.
example:


```
if (collision.CompareTag("Package") && !hasPackage)
{
hasPackage = true;
GetComponent<ParticleSystem>().Play();
Destroy(collision.gameObject, delay);
}
```
# توضیحات درباره ی گرفتن  یک بسته توسط چیزی :
```
hasPackage=true
```
یعنی بسته رو گرفته 
____
```
hasPackage=false
```
یعنی بسته  تحویل داده 
----------
```
if (collision.CompareTag("Package") && !hasPackage)
```
میاد میگه تو شرط رو باید رعایت کنی یکی این که بسته رو گرفته باشی و از قبل نداشته باشی بسته و به بسته برخورد کرده باشی
____
