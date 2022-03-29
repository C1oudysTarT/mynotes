### Cyclegan-VC2的改进版本

#### 来源与出处

+ 来自Cyclegan-VC2的同一组，ICASSP-21

#### 创新点

+ 针对CycleGAN-VC2中存在的捕捉时频结构能力不足、时频一致性损失较大的问题，提出使用FIF（即**填充帧**）的方式来解决此问题

  ![image-20220329144258853](https://raw.githubusercontent.com/C1oudysTarT/mynotes/main/img/202203291442907.png)

+ FIF的结构图，对给定的源Mel谱图**x**，首先创建一个临时Mask **m**，其大小与**x**相同，其部分值为0（对应下图中的黑色区域），其余值为1（对应白色区域）。黑色区域是基于预定规则（4.2节中描述）确定的。然后对**x**进行点乘，<img src="https://raw.githubusercontent.com/C1oudysTarT/mynotes/main/img/202203291456594.png" alt="image-20220329145604557" style="zoom:50%;" />。因此所得到的图像，黑色区域被屏蔽，白色区域保持不变。

![image-20220329144726778](https://raw.githubusercontent.com/C1oudysTarT/mynotes/main/img/202203291456518.png)

+ 这种方法主要是受到图像修复等领域中的complementation-based自监督学习所启发。

