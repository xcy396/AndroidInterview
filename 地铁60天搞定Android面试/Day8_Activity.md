# Day：Activity
1、Task是Activity的集合，采用栈的方式来管理其中的Activity，称为返回栈或任务栈。

2、任务栈中的Activity采用后进先出的方式。

3、Activity的taskAffinity用于指定Activity更愿意依附于哪一个任务，默认情况下同一个应用的所有Activity的taskAffinity都相同，就是应用包名。

4、Activity A启动Activity B，B可以自己定义如何与当前任务关联（使用AndroidManifest定义），也可以由A来决定B如何与当前任务关联（使用Intent的flag）。

5、二者同时设置时Intent的flag级别更高。

## Activity的启动模式
1、standard模式是默认模式，每次启动都会创建新的Activity实例。

2、singleTop模式先判断任务栈栈顶是否有目标Activity实例，有则直接回调onNewIntent，无则创建新实例。

3-1、singleTask模式下，先根据taskAffinity检查Activity所需的任务栈是否存在，不存在就创建任务栈创建新实例；

3-2、所需任务栈存在就看任务栈中有没有目标实例，有则直接回调onNewIntent并把实例之上所有的Activity出栈，无则创建新实例；

3-3、如果目标任务栈位于后台会直接把整个任务栈移到前台来。

4、singleInstance模式下，先判断是否存在实例，有则直接回调onNewIntent。无则创建一个新的任务栈和新的实例，该任务栈中不允许再有其他实例。

## Activity启动模式应用场景
1、standard模式为默认模式，适用于大多数场景。

2、singleTop模式适用于登录页面等。

3、singleTask模式适用于主页面等。

4、singleInstance模式适用于多个程序使用一个Activity，如系统launcher、来电界面等。

## Intent的Flag
1-1、FLAG_ACTIVITY_NEW_TASK最为常用，目的是让Activity在它的目标taskAffinity对应的任务栈中启动。

1-2、如果目标任务栈在后台会移到前台，目标任务栈不存在会新建任务栈？

1-3、非Activity（如Service）启动Activity时，需要显示设置FLAG_ACTIVITY_NEW_TASK。

1-4、Activity启动Activity时，singleTask模式和singleInstance模式隐式的设置了FLAG_ACTIVITY_NEW_TASK，而standard模式和singleTop模式不会设置。



