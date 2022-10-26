# StartEasing
关于Unity的缓动数学库
# 使用方式
例如下方是一个线性插值，3秒内，从0到10.
```
float duration = 3f;
float num = 0f;
float timer = 0f;

private void Update()
{
    if (timer < duration)
    {
        //float t = timer / duration; //作为对比，这是没有缓动动画的
        float t = StartFramework.Easing.Bounce.EaseOut(timer, duration); //使用了此库，获得了EaseOutBounce动画
        num = Mathf.Lerp(0f, 10f, t);
        timer += Time.deltaTime;
    }
    else
    {
        num = 10f;
    }

    Debug.Log(num);
}
```
