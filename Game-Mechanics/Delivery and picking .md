```
 bool hasPackage=false;
    int packageCount=0;

    [SerializeField]float delay=3f;
    [SerializeField]int totalpackage=7;


    
     void OnTriggerEnter2D(Collider2D collision) {
        if(collision.CompareTag("package"))
        {
            packageCount++;
            hasPackage=true;
            Destroy(collision.gameObject ,delay);
            Debug.Log("package:"+ packageCount);
        }
        if (collision.CompareTag("deliverypoint"))
        {
            if(hasPackage && packageCount == totalpackage)
            {
                Debug.Log("oll done!");
                hasPackage=false;
                packageCount=0;
            }
            else
            {
                Debug.Log("not done!");
            }
        }
              
    }
```
