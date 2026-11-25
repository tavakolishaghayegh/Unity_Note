```
using UnityEngine;
using UnityEngine.SceneManagement;
using TMPro;
using System;

public class delivery : MonoBehaviour
{
   
    [SerializeField] TMP_Text packagetext;
    [SerializeField] TMP_Text scoretext;
    int packageCount=0;
    int score=0;

    void Start()
{
    
     UpdateScoreText();
     UpdatePackageText();
}
    void UpdatePackageText()
    {
        packagetext.text = "Packages: " + packageCount + "/" + totalpackage;
        
    }
    void UpdateScoreText()
    {
        scoretext.text = "Score: " + score;

        
    }


    
     void OnTriggerEnter2D(Collider2D collision) {
        if(collision.CompareTag("package"))
        {
            packageCount++;
            score+=100;
            UpdateScoreText();
            UpdatePackageText();
        }
        if (collision.CompareTag("deliverypoint"))
        {
            if(hasPackage && packageCount == totalpackage)
            {
                packageCount=0;
                score-=50;
                
             UpdatePackageText();
            
        }
              
    }

}
```
