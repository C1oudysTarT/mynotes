### StarGAN-VC2

#### 来源与出处

---



+ 同样是日本NTT电讯公司
+ interspeech-2019

#### 与CycleGAN-VC2的异同

---



+ 相同之处：
  1. 都是非并行的VC，不依赖并行数据
  2. 损失函数组成部分相似（例如GAN损失，身份损失，循环一致性损失等等）
  3. StarGAN-VC是由CycleGAN-VC延伸而来，通过加入**域迁移**的方式来实现仅用一个生成器就可以实现非并行的跨域迁移。
+ 不同之处：
  1. 一对多的方法，不同于CycleGAN-VC的一对一。
  2. 效果上有差异，转换结果略差于CycleGAN-VC

#### 创新点

---



+ 三种情况，分别是过往做法中的分类损失和目标条件对抗损失，以及本文提出的源-目标条件对抗损失

  ![image-20220331153847189](/Users/roygan/Library/Application Support/typora-user-images/image-20220331153847189.png)

+ 在StarGAN-VC中，目标是获得**一个单独**的，可以学习多个域（多个语者）的生成器，即
  $$
  G(x,c') -> x'
  $$
  其中*c*代表对应的域代码。

+ StarGAN-VC由StarGAN启发而来，因此有对抗性损失(adv loss)，分类损失(classification loss)和循环一致性损失(cycle-consisstency loss)。但与StarGAN不同的是，StarGAN-VC采取了类似于CycleGAN-VC中的身份映射损失(identity-mapping loss)来保持语音的组成。
+ 

