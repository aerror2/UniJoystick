# UniJoystick
> It is a very cool Joystick made with less than 100 lines of codes.

> With a simple and clear configuration as well as  the UI hierarchy structure.

![](DocAssets/Interface.png)

> How to use?

1. Get instance of the Joystick
2. Register OnValueChanged event
3. then just hit the Play button,ha..

```
    public float speed = 5;
    [SerializeField] Joystick joystick;
    void Start()
    {
        joystick.OnValueChanged.AddListener(v =>
        {
            if (v.magnitude != 0)
            {
                transform.Translate(v.x * speed, 0, v.y * speed, Space.World);
                transform.rotation = Quaternion.LookRotation(new Vector3(v.x, 0, v.y));
            }
        });
    }
```

![](DocAssets/UniJoystick.gif)

> My Blog

[[Unity 3d] 使用UGUI做一个类似王者荣耀的摇杆 - 简书]( https://www.jianshu.com/p/2b2cdccafef4)