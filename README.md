# activity-stack-task
Understand Tasks and Back Stack

1、 https://developer.android.com/guide/components/activities/tasks-and-back-stack 是对Android activity task和stack的理解
2、深入理解activity的四种启动模式，standard、singleTop、singleTask、singleinstance
3、taskaffinity 栈亲和性的理解
任务栈标示，搭配singleTask或者Intent.FLAG_ACTIVITY_NEW_TASK 可以显示不同于启动activity的TaskRecord。

4、allowTaskReparent为true的理解。a 应用的A activity设置为该属性；当应用b启动 a应用A activity时，A activity跟b应用的启动activity属于同一个TaskRecord

5、adb shell dumpsys activity activities任务栈打印。
