# rotation :
```
transform.Rotate(0, 0, Z);
```
• در Start آبجکت فقط یک بار می‌چرخد.
• در Update آبجکت به‌صورت مداوم می‌چرخد.
______________________________________________________________________________________________________________
# move :
```
transform.Translate(x, y, z);
```
in update :
```
transform.Translate(x, y * Time.deltaTime, z);
```
______________________________________________________________________________
Example of rotation and moving  :
```
[SerializeField] float steerSpeed = 1f;
[SerializeField] float moveSpeed = 0.01f;
void Update()
{
transform. Rotate(0, 0, steerSpeed);
transform. Translate(0, moveSpeed, 0);
}
```
_____________________________________________________________________ 
# use keyboards for move and rotate :
```
using UnityEngine.InputSystem;

        if (Keyboard.current.wKey.isPressed)
        {
            move = 1f;
            }

        else if (Keyboard.current.sKey.isPressed)
        {
            move = -1f;
        }

        if (Keyboard.current.aKey.isPressed)
        {
            steer = 1f;
        }


        else if (Keyboard.current.dKey.isPressed)
        {
            steer= -1f;
        }
```
___________________________________________________________
# Using Time deltaTime
 • Using Time. deltaTime Unity can tell us how long each frame took to execute.
 ```
void Update()
{
    transform.Translate(0, 0, 10 * Time.deltaTime);
}
```
_________________________________________________________________
# OnTriggerEnter
 
 برای تشخیص ورود یک آبجکت به محدود تریگر.  
 ```
void OnTriggerEnter2D(Collider2D collision)
{
    // دستوراتی که هنگام ورود آبجکت اجرا می‌شوند
}
```


______________________________________________________________________
# OnCollisionEnter2D  
 
برای تشخیص برخورد فیزیکی بین دو آبجکت.
```
void OnCollisionEnter2D(Collision2D collision)
{
    // Code runs when a collision occurs
}
```


___________________________________________________________________________
# If Statements
• If statements let us check if something is true or not and then do something based upon the result.
```
if (condition)
{
    // Code executes if condition is true
}
```
Example :
```
if(collision.CompareTag("Package") && !hasPackage )
        {
             Debug.Log("picked up Package");
             hasPackage= true;
             GetComponent<ParticleSystem>().Play();
             Destroy(collision.gameObject , delay);
        }

```
_______________________________________________________________________________________________
# bool
 A bool is a data type that stores only two possible values: true or false.
```
bool hasPackage;
```
Example :
```
 if(collision.CompareTag("customer") && hasPackage)
        {
             Debug.Log("picked up Package");
             hasPackage= false;
             GetComponent<ParticleSystem>().Stop();
              Destroy(collision.gameObject);
        }

```
متغیر hasPackage وضعیت داشتن بسته رو کنترل می‌کنه:
• true = ماشین بسته دارد.
• false = ماشین بسته ندارد.
```
if(collision.CompareTag("Package") && !hasPackage )
        {
             Debug.Log("Deliverd package");
             hasPackage= true;
             GetComponent<ParticleSystem>().Play();
             Destroy(collision.gameObject , delay);
        }
```
_____
در این مثال ها بسته رو گرفته  بعد که تحویل میده بسته رو فالس میکنه که بسته ای نباشه دیگه  و ابجکت مشتری حذف میشه
_____________________________________________
# Destroy ()
```
Destroy ();
```
 • Use [SerializeField] so that we can tune how long the delay is before destroy or disappears.
 ```
[SerializeField] float delay = f ;
Destroy(collision.gameObject, delay);
```
Example :
```
[SerializeField] float delay = 1f ;
if(collision.CompareTag("Package") && !hasPackage )
        {
             
             Destroy(collision.gameObject , delay);
        }
```
______________________________________________________
# بسته مثل یک آیتم قابل جمع‌آوری عمل می‌کنه، استفاده از OnTriggerEnter2D() انتخاب مناسبیه.
```
 void OnTriggerEnter2D(Collider2D collision) 
    {
        
        if(collision.CompareTag("Package") && !hasPackage )
        {
             Debug.Log("picked up Package");
             hasPackage= true;
             GetComponent<ParticleSystem>().Play();
             Destroy(collision.gameObject , delay);
        }
```
________________________________________________________
# !hasPackage
```
if (collision.CompareTag("Package") && !hasPackage)
```
. آبجکت برخوردشده باید تگ Package داشته باشد.
2. ماشین نباید از قبل بسته‌ای داشته باشد
___________________________________________________
# Change color or effect after get package 

```
   GetComponent<ParticleSystem>().Play();
```
______________________________
#  GetComponent<>
GetComponent<>(): Used to access a specific Component attached to the same GameObject.  

Example :  
```
void OnCollisionEnter2D(Collision2D collision)
{
    GetComponent<AudioSource>().Play();
}
```
________________________
# Average speed :
boost tag
```
[SerializeField]float CurrentSpeed = 6f;
[SerializeField] float boostSpeed =10f;
[SerializeField] float regularSpeed=5f;

void OnTriggerEnter2D(Collider2D collision) {
        if(collision.CompareTag("boost"))
        {
         CurrentSpeed= boostSpeed;
           
    }
```
___________________________________
      








