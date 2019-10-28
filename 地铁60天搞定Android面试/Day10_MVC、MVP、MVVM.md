# Day：MVC、MVP、MVVM
1、Model模型对象中存储着数据和业务逻辑，应用的全部模型对象组成了模型层；

2、View视图对象知道如何在屏幕上绘制自己及如何响应用户的输入、触摸，凡是屏幕上能看到的对象就是视图对象，全部视图对象组成了视图层；

3、Controller控制对象含有应用的逻辑单元，是视图和模型对象联系的纽带，响应视图对象触发的各类事件，同时管理着模型对象和视图间的数据流动。

4、MVC模式的工作流程为：视图对象触发各类事件交由控制对象分发，控制对象选取合适的模型对象处理事件，模型对象处理完事件后再由控制对象通知视图对象进行更新视图。

5、Android开发原始写法中，Activity中包含了Controller对象、Model对象及部分View对象的代码，异常臃肿。

6、原始写法->MVC模式：将Activity中的业务逻辑代码也就是Model层进行抽离，称为Model层。这样Activity仅负责Controller层和部分View层，业务与视图进行了分离。

7、MVC模式->MVP模式：将Activity中的程序逻辑控制代码也就是Controller层进行抽离，称为Presenter层，这样Activity仅负责View层，解耦更彻底。

8、MVC模式->MVVM模式：将View层和Presenter层之间的交互做成自动化的，将Presenter层改名为ViewModel层。