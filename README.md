# Anisotropic-PDF
![logo](https://github.com/worlddatong/Anisotropic-PDF/blob/main/imgs/4.png)

# 简介
Anisotropic PDF是一款生成各项异性原子对分布函数(atomic pair-distribution function, PDF)曲线的处理软件。
在外部刺激下(电场/应变)，样品对应的各向同性(isotropic)PDF则会表现出三维上的各向异性。

因此，我们需要从三维<img src="https://latex.codecogs.com/svg.image?\vec{r}&space;" title="\vec{r} " />空间来分析各向异性PDF曲线<img src="https://latex.codecogs.com/svg.image?G(\vec{r})" title="G(\vec{r})" />。

Anisotropic PDF可以对输入的二维平面探测器不同角度的<img src="https://latex.codecogs.com/svg.image?S(Q)" title="S(Q)" />

1. 进行球谐分解，得到对应的球谐系数<img src="https://latex.codecogs.com/svg.image?S_l^m(Q)" title="S_l^m(Q)" />。
2. 通过球谐系数，重构散射矢量<img src="https://latex.codecogs.com/svg.image?\vec{Q}" title="\vec{Q}" />平行于特定方向的<img src="https://latex.codecogs.com/svg.image?S(\vec{Q})" title="S(\vec{Q})" />。
3. 通过球谐系数，计算原子对密度函数(atomic pair-density function)的球谐分量<img src="https://latex.codecogs.com/svg.image?\rho_l^m(r)" title="\rho_l^m(r)" />，从而得到各向异性的PDF曲线<img src="https://latex.codecogs.com/svg.image?G(\vec{r})" title="G(\vec{r})" />。

# 下载
[Download](https://github.com/worlddatong/Anisotropic-PDF/releases)
  
# 界面
![GUI1](https://github.com/worlddatong/Anisotropic-PDF/blob/bc42618367489cc0f1abdb713cd130f88e90dc05/imgs/5.png)

# 使用指南
- 数据准备
1. 使用[Fit2D](https://www.esrf.fr/computing/scientific/FIT2D/)、[Dioptas](https://github.com/Dioptas/Dioptas)等工具,根据与电场不同夹角，将加电场样品的二维衍射谱分割积分为一维衍射谱<img src="https://latex.codecogs.com/svg.image?(2\theta,&space;I)" title="(2\theta, I)" />。
2. 使用[PDFgetX3](https://www.diffpy.org/products/pdfgetx.html)、[Gudrun](https://www.isis.stfc.ac.uk/Pages/Gudrun.aspx)等工具，将<img src="https://latex.codecogs.com/svg.image?(2\theta,&space;I)" title="(2\theta, I)" />处理转化为<img src="https://latex.codecogs.com/svg.image?(Q,S(Q))" title="(Q,S(Q))" />，其中<img src="https://latex.codecogs.com/svg.image?\inline&space;Q" title="\inline Q" />为散射矢量(scattering vector)的模，<img src="https://latex.codecogs.com/svg.image?\inline&space;S(Q)" title="\inline S(Q)" />为对应的总散射结构函数(total scattering structure function)。

- 数据格式
1. S(Q)数据文件格式：2列n行数据，第一列为<img src="https://latex.codecogs.com/svg.image?Q" title="Q" />数据，第二列为<img src="https://latex.codecogs.com/svg.image?\inline&space;S(Q)" title="\inline S(Q)" />数据

- 软件使用
1. 点击"Load S(Q)"加载多组S(Q)数据，加载后在"Angle with E-field(degree)"中填写该组数据对应的与电场夹角。可以通过"Delete selected row"删除选定数据或"Clear grid"清除所有加载数据。
2. 设定球谐函数阶数L，默认为2。注意S(Q)数据的组数必须大于球谐函数阶数L。
3. 设定原子对r，在"rmin"、"rmax"、"rstep"中分别填入原子对的最小值，最大值与间隔。
4. 设定原子对方向矢量，可以选择"the r direction vector"填写矢量分量X, Y, Z；或选择"the polar and azimuthal angle(degree)"填写球坐标分量<img src="https://latex.codecogs.com/svg.image?\theta" title="\theta" />, <img src="https://latex.codecogs.com/svg.image?\varphi" title="\varphi" />。
5. 点击"Set Output folder"，设定输出文件夹，软件的计算结果都会保存在该文件夹内。
6. 在"Wave length"处输入实验所用X射线的波长。
7. 选择"Output expansion coefficients Slm(Q)"， "Output reconstructed S(Q)"和"Output G(r)"，来确认是否保存球谐系数<img src="https://latex.codecogs.com/svg.image?S_l^m(Q)" title="S_l^m(Q)" />，重构的<img src="https://latex.codecogs.com/svg.image?(Q,S(Q))" title="(Q,S(Q))" />和各向异性PDF<img src="https://latex.codecogs.com/svg.image?G(\vec{r})" title="G(\vec{r})" />。
8. 点击"Calculate the selected"执行运算，可以在命令窗口观察到程序运行情况与报错信息。

![GUI2](https://github.com/worlddatong/Anisotropic-PDF/blob/main/imgs/6.png)![cmd1](https://github.com/worlddatong/Anisotropic-PDF/blob/main/imgs/7.png)

# 参考文献
1. Egami, Takeshi, and Simon JL Billinge. *Underneath the Bragg peaks: structural analysis of complex materials*. Elsevier, 2003.
2. Usher, Tedi-Marie, et al. "Electric-field-induced local and mesoscale structural changes in polycrystalline dielectrics and ferroelectrics." *Scientific reports* 5.1 (2015): 1-10.
3. Suzuki, Y., J. Haimovich, and T. Egami. "Bond-orientational anisotropy in metallic glasses observed by x-ray diffraction." *Physical Review B* 35.5 (1987): 2162.
4. Egami, T., et al. "Deformation induced bond orientational order in metallic glasses." *Journal of non-crystalline solids* 192 (1995): 591-594.

# 引用
如果Anisotropic PDF对您的研究有帮助，请引用这个网址：
https://github.com/worlddatong/Anisotropic-PDF
