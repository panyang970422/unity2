# homework3
[Blog](http://sysu.cf/?p=22)
## 游戏对象运动的本质

- 游戏对象位置的改变

```c++

void Update ()
{
    this.transform.position += Vector3.left * Time.deltaTime;
}
```

## 抛物线

- transform.positon & vector3

```c++
private int speed;
private int gravity;
void Start ()
{
    this.speed = 1;
    this.gravity = 9.8;
}

void Update () 
{
    this.transform.position += speed * Vector3.left * Time.deltaTime;
    this.transform.position += gravity * Time.deltaTime * Time.deltaTime / 2 * Vector3.down ;
}
```

- transform.translate & vector3

```c++
private int speed;
private int gravity;
void Start ()
{
    this.speed = 1;
    this.gravity = 9.8;
}

void Update ()
{
    this.transform.Translate(speed * Vector3.left * Time.deltaTime);
    this.transform.Translate(gravity * Time.deltaTime * Time.deltaTime / 2 * Vector3.down) ;
}
```

- Using Rigidbody

```c++
using UnityEngine;
using System.Collections;

public class ExampleClass : MonoBehaviour
{
    public Rigidbody rb;
    void Start()
    {
        rb = GetComponent<Rigidbody>();
        rigidbody.velocity =new Vector3 (3, 10, 0);
    }

    void FixedUpdate()
    {
    }
}
```

## Solar System

```c++
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class AllSolar: MonoBehaviour {
    public Transform Sun;
    public Transform Mercury;
    public Transform Venus;
    public Transform Earth;
    public Transform Moon;
    public Transform Mars;
    public Transform Jupiter;
    public Transform Saturn;
    public Transform Uranus;
    public Transform Neptune;
    void Start()
    {
        Sun.position = Vector3.zero;
        Mercury.position = new Vector3(2, 0, 0);
        Venus.position = new Vector3(-4, 0, 0);
        Earth.position = new Vector3(6, 0, 0);
        Mars.position = new Vector3(-8, 0, 0);
        Jupiter.position = new Vector3(-10, 0, 0);
        Saturn.position = new Vector3(12, 0, 0);
        Uranus.position = new Vector3(-14, 0, 0);
        Neptune.position = new Vector3(16, 0, 0);
    }
    // Update is called once per frame
    void Update()
    {
        Earth.RotateAround(Sun.position, new Vector3(0, 1.3f, 0), 30 * Time.deltaTime);
        Moon.RotateAround(Earth.position, new Vector3(0, 1.0f, 0), 30 * Time.deltaTime);
        Mercury.RotateAround(Sun.position, new Vector3(0, 1.2f, 0), 47 * Time.deltaTime);
        Venus.RotateAround(Sun.position, new Vector3(0, 1.3f, 0), 35 * Time.deltaTime);
        Mars.RotateAround(Sun.position, new Vector3(0, 1.4f, 0), 24 * Time.deltaTime);
        Jupiter.RotateAround(Sun.position, new Vector3(0, 1.2f, 0), 13 * Time.deltaTime);
        Saturn.RotateAround(Sun.position, new Vector3(0, 0.8f, 0), 9 * Time.deltaTime);
        Uranus.RotateAround(Sun.position, new Vector3(0, 0.7f, 0), 6 * Time.deltaTime);
        Neptune.RotateAround(Sun.position, new Vector3(0, 0.6f, 0), 5 * Time.deltaTime);

        Earth.Rotate(Vector3.up * Time.deltaTime * 250);
        Moon.Rotate(Vector3.up * Time.deltaTime * 220);
        Mercury.Rotate(Vector3.up * Time.deltaTime * 300);
        Venus.Rotate(Vector3.up * Time.deltaTime * 280);
        Mars.Rotate(Vector3.up * Time.deltaTime * 220);
        Jupiter.Rotate(Vector3.up * Time.deltaTime * 180);
        Saturn.Rotate(Vector3.up * Time.deltaTime * 160);
        Uranus.Rotate(Vector3.up * Time.deltaTime * 150);
        Neptune.Rotate(Vector3.up * Time.deltaTime * 140);
    }
}
```
