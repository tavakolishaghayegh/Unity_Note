# محاسبه حرکت :
```
float moveAmount = move * CurrentSpeed * Time.deltaTime;
```
میزان حرکت آبجکت را بر اساس ورودی بازیکن، سرعت فعلی و زمان محاسبه می‌کند
______________________________________________________________
# محاسبه چرخش
```
float = steer * steerSpeed * Time.deltaTime;
```
میزان چرخش آبجکت را بر اساس ورودی چرخش و سرعت چرخش محاسبه می‌کند
________________________________________
# حرکت آبجکت
```
transform.Translate(0, moveAmount, 0);
```
______________________________________________
# چرخش آبجکت
```
transform.Rotate(0, 0, steerAmount);
```
__________________________________
Example :
```
float move = 1f;
float steer = 1f;
float CurrentSpeed = 10f;
float steerSpeed = 100f;

float moveAmount = move * CurrentSpeed * Time.deltaTime;
float steerAmount = steer * steerSpeed * Time.deltaTime;

transform.Translate(0, moveAmount, 0);
transform.Rotate(0, 0, steerAmount);
```
