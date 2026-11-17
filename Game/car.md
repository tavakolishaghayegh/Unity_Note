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
