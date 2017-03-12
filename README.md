##一个会自动寻路的小滑块
###version：4.0

###warn:暂时只支持能运行es6的浏览器如Chrome
<hr>
<br>
##使用方法（1.0版本）
- 在输入框中允许输入如下指令，按下按钮后，使得正方形做相应动作
- GO：向蓝色边所面向的方向前进一格（一格等同于正方形的边长）
- TUN LEF：向左转（逆时针旋转90度）
- TUN RIG：向右转（顺时针旋转90度）
- TUN BAC：向右转（旋转180度）
- 移动不能超出格子空间
<br>

###2.0版本新增命令（向后兼容）
- TRA LEF：向屏幕的左侧移动一格，方向不变
- TRA TOP：向屏幕的上面移动一格，方向不变
- TRA RIG：向屏幕的右侧移动一格，方向不变
- TRA BOT：向屏幕的下面移动一格，方向不变
- MOV LEF：方向转向屏幕左侧，并向屏幕的左侧移动一格
- MOV TOP：方向转向屏幕上面，向屏幕的上面移动一格
- MOV RIG：方向转向屏幕右侧，向屏幕的右侧移动一格
- MOV BOT：方向转向屏幕下面，向屏幕的下面移动一格
<br>

###3.0版本新增功能
- 命令输入框由input变为textarea，可以允许输入多条指令，每一行一条
- textarea左侧有一列可以显示当前行数的列（代码行数列），列数保持和textarea中一致
- 当textarea发生上下滚动时，代码行数列同步滚动
- 能够判断指令是否合法，不合法的指令给出提示
- 点击执行时，依次逐条执行所有命令
- 对于GO，TRA以及MOV指令增加可以移动格子数量的参数，例如
- GO 3：向当前方向前进三格
- TRA TOP 2：向屏幕上方平移两格
- MOV RIG 4：方向转向屏幕右侧，向屏幕的右侧移动四格
- 命令不区分大小写
<br>

###4.0版本新增功能
- 新增元素“墙”，墙是正方形不可进入、越过的区域
- 新增修墙的指令，BUILD，执行指令时，会在当前方块面对的方向前修建一格墙壁，如果被指定修墙的地方超过边界墙或者已经有墙了，则取消修墙操作，并调用浏览器的console.log方法打印一个错误日志
- 新增粉刷的指令，BRU color，color是一个字符串，保持和css中颜色编码一致。执行指令时，如果当前方块蓝色边面对方向有紧相邻的墙，则将这个墙颜色改为参数颜色，如果没有，则通过调用浏览器的console.log方法，打印一个错误日志
- 新增一个按钮，可以在空间内随机生成一些墙
- 增加一个指令：MOV TO x, y，会使得方块从当前位置移动到坐标为x，y的地方，移动过程中不能进入墙所在的地方，实现了自动寻路算法
<br>

[开启小车吧！](https://Reusjs.github.io/task33_1/task33.html "demo")
