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
________________________________________________________________________________________-






