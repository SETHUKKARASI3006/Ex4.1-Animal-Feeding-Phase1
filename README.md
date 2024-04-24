# Ex4.1-Animal-Feeding-Phase1
## Aim:
To develop a animal feeding game-Phase-1 using unity.

## Algorithm:
### Player Controller:
#### Step 1: 
Extract the package and in unity , asserts -> Import packages -> Custom packages and select the package. When we go to Assets folders we can see the course library which we extracted.

#### Step 2: 
If you want, drag a different material from Course Library -> Materials onto the Plane object.

#### Step 3: 
Drag 1 Human, 6 Animals, and 1 Food object into the Hierarchy.

#### Step 4: 
Modify the position of the animals and food so you can see them clearly.

#### Step 5: 
Adjust the XYZ scale of the food so you can easily see it in the scene.

#### Step 6: 
In your Assets folder, create a new “PlayerControll” script inside.Attach the script to the Player by dragging the C# file to the player and open in the inspector and check whether it is attached.

### Moving Controller:
#### Step 1: 
Create a new “MoveForward” script, attach script to the Food banana by dragging the C# file to the banana and open in the inspector and check whether it is attached.

#### Step 2: 
Create a new “Prefab” folder, drag your food (banana) into Prefab folder, and a pop up raises-> choose "Original Prefab".

#### Step 3: 
Select the Player in the hierarchy, then drag the banana from your Prefab folder onto the new Projectile Prefab box in the inspector.

#### Step 4: 
Select all six animals in the hierarchy and Add Component -> Drag the 'MoveForward' script from the Assests into inspector.

#### Step 5: 
Edit their speed values and test to see how it looks. Drag all six animals into the Prefab folder, by choosing “Original Prefab”.

## rogram:
NAME : SETHUKKARASI C

REG NO: 212223230201

### PROGRAM CONTROLLER:
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class PlayerControl : MonoBehaviour
{
    public float horizontalInput;
    public float speed = 10.0f;
    public float xRange = 10f;
    public GameObject projectilePrefab;
    // Start is called before the first frame update
    void Start()
    {

    }

    // Update is called once per frame
    void Update()
    {
        if (transform.position.x < -xRange)
        {
            transform.position = new Vector3(-xRange, transform.position.y, transform.position.z);
        }
        if (transform.position.x > xRange)
        {
            transform.position = new Vector3(xRange, transform.position.y, transform.position.z);
        }
        horizontalInput = Input.GetAxis("Horizontal");
        transform.Translate(Vector3.right * horizontalInput * Time.deltaTime * speed);
        if (Input.GetKeyDown(KeyCode.Space))
        {
            Instantiate(projectilePrefab, transform.position, projectilePrefab.transform.rotation);
        }
    }
}

```

### MOVE FORWARD:
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class MoveForward : MonoBehaviour
{
    public float speed = 40.0f;
    // Start is called before the first frame update
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        transform.Translate(Vector3.forward*Time.deltaTime*speed);
    }
}

```
## Output:
![output](image.png)

## Result:
Animal feeding game-Phase-1 using unity is developed successfully.