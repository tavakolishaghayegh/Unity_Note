```
void Move()
    {
       
        Vector2 movement = Vector2.zero;

if (Keyboard.current.upArrowKey.isPressed)
    movement.y = 1;

if (Keyboard.current.downArrowKey.isPressed)
    movement.y = -1;

if (Keyboard.current.rightArrowKey.isPressed)
    movement.x = 1;

if (Keyboard.current.leftArrowKey.isPressed)
    movement.x = -1;
        

        
        myRigidbody.linearVelocity=transform.up * movement.y * movespeed;
        if (movement.y != 0)

    {

        float rotation = -movement.x * steerSpeed * Time.deltaTime* movement.y;
        myRigidbody.MoveRotation(myRigidbody.rotation+ rotation);

    

    }
```
