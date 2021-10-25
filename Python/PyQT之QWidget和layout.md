### PyQT之QWidget和layout

**问题背景**：每次出现layout设置时都会伴随着QWidget的出现

**问题**：layout与QWidget到底是何关系？二者是绑定的吗？



**解释**：

一般初始化一个QMainWindow之后，就可以对这个window做我们想要的布局操作，尽情的施展才艺来设计完成我们的UI，但是值得一提的是，QMainWindow是默认有一个layout的，所以再次设置layout会失效，那肯定不行啊，我们的UI设计包罗万象，这样就会局限住我们的操作。所以如果我们想要在不同的区域实现不同的功能，那就得对整个window做一个分割，每个区域对应一个功能的实现。那么问题就来了，怎么分割，怎么分解整个window的layout，<font color=red>一个好的做法就是加QWidget，通过增加多个QWidget，可以对应增加多个layout，再把这多个QWidget加载到整个window的layout上，就可以完美的做到分割。</font>可以再好奇一点，其实我们前面提到的QMainWindow，它也是继承自QWidget的。因为QMainWindow有自己的layout，==所以通用的做法是，在其之上加载一个QWidget，然后在这个QWidget之上加载一个GridLayout，通过网格布局控制，我们再在这个网格布局之上继续增加其它的QWidget来实现对整个窗口的切分，来达到不同区域不同布局的目的==

