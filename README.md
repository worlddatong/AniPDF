# AniPDF
![logo](https://github.com/worlddatong/Anisotropic-PDF/blob/main/imgs/9.png)

# Introduction
AniPDF is a graphical user interface (GUI) software based on the spherical harmonic method to process anisotropic total scattering data interactively.
AniPDF是一款生成各向异性原子对分布函数(atomic pair-distribution function, PDF)曲线的处理软件。
Egami等人[1]提出，样品在外部刺激下(电场/应变)，其各向同性(isotropic)PDF则会表现出三维上的各向异性，而球谐函数可以有效地来描述这种各向异性。

因此，要分析在外部刺激下样品的局部微观结构，就需要从三维<img src="https://latex.codecogs.com/svg.image?\inline&space;\vec{r}" title="\inline \vec{r}" />空间来分析各向异性PDF曲线<img src="https://latex.codecogs.com/svg.image?\inline&space;G(\vec{r})" title="\inline G(\vec{r})" />。目前，Usher等人[2]与Egami等人[3,4]等人都报道了利用各向异性PDF来分析多晶陶瓷、金属玻璃等材料的局部微观结构。

AniPDF软件可以对输入的二维平面探测器不同角度的总散射结构函数(total scattering structure function)<img src="https://latex.codecogs.com/svg.image?\inline&space;S(Q)" title="\inline S(Q)" />：

1. 进行球谐分解，得到对应的球谐系数<img src="https://latex.codecogs.com/svg.image?\inline&space;S_l^m(Q)" title="\inline S_l^m(Q)" />。
2. 通过球谐系数，重构散射矢量<img src="https://latex.codecogs.com/svg.image?\inline&space;\vec{Q}" title="\inline \vec{Q}" />平行于特定方向的<img src="https://latex.codecogs.com/svg.image?\inline&space;S(\vec{Q})" title="\inline S(\vec{Q})" />。

3. 通过球谐系数，计算原子对密度函数(atomic pair-density function)的球谐分量<img src="https://latex.codecogs.com/svg.image?\inline&space;\rho_l^m(r)" title="\inline \rho_l^m(r)" />，从而得到各向异性的PDF曲线<img src="https://latex.codecogs.com/svg.image?\inline&space;G(\vec{r})" title="\inline G(\vec{r})" />。

# Download
- Windows: [Download](https://github.com/worlddatong/Anisotropic-PDF/releases)
- Linux: [Download](https://github.com/worlddatong/Anisotropic-PDF/releases)
  
# GUI
![GUI1](https://github.com/worlddatong/Anisotropic-PDF/blob/main/imgs/5.png)

# 使用指南
- 数据准备
1. 使用[Fit2D](https://www.esrf.fr/computing/scientific/FIT2D/)、[Dioptas](https://github.com/Dioptas/Dioptas)等工具,根据与电场不同夹角，将加电场样品的二维衍射谱分割积分为一维衍射谱<img src="https://latex.codecogs.com/svg.image?\inline&space;(2\theta,&space;I)" title="\inline (2\theta, I)" />。
2. 使用[PDFgetX3](https://www.diffpy.org/products/pdfgetx.html)、[Gudrun](https://www.isis.stfc.ac.uk/Pages/Gudrun.aspx)等工具，将<img src="https://latex.codecogs.com/svg.image?\inline&space;(2\theta,&space;I)" title="\inline (2\theta, I)" />处理转化为<img src="https://latex.codecogs.com/svg.image?\inline&space;(Q,S(Q))" title="\inline (Q,S(Q))" />，其中<img src="https://latex.codecogs.com/svg.image?\inline&space;Q" title="\inline Q" />为散射矢量(scattering vector)的模，<img src="https://latex.codecogs.com/svg.image?\inline&space;S(Q)" title="\inline S(Q)" />为对应的总散射结构函数(total scattering structure function)。

- 数据格式
1. <img src="https://latex.codecogs.com/svg.image?\inline&space;S(Q)" title="\inline S(Q)" />数据文件格式：2列n行数据，第一列为<img src="https://latex.codecogs.com/svg.image?\inline&space;Q" title="\inline Q" />数据，第二列为<img src="https://latex.codecogs.com/svg.image?\inline&space;S(Q)" title="\inline S(Q)" />数据。
2. 输入软件的各组<img src="https://latex.codecogs.com/svg.image?\inline&space;S(Q)" title="\inline S(Q)" />数据必须具有相同的<img src="https://latex.codecogs.com/svg.image?\inline&space;Q" title="\inline Q" />值。

- 软件使用
4. 点击"Load S(Q)s"加载多组<img src="https://latex.codecogs.com/svg.image?\inline&space;S(Q)" title="\inline S(Q)" />数据，加载后在"Angle with E-field(degree)"中填写该组数据对应的与电场夹角。可以通过"Delete selected row"删除选定数据或"Clear grid"清除所有加载数据。
5. 设定球谐函数阶数L，默认为2。注意<img src="https://latex.codecogs.com/svg.image?\inline&space;S(Q)" title="\inline S(Q)" />数据的组数必须大于球谐函数阶数L。
6. 设定原子对r，在"rmin"、"rmax"、"rstep"中分别填入原子对的最小值，最大值与间隔。
7. 设定原子对方向矢量，可以选择"the r direction vector"填写矢量分量X, Y, Z；或选择"the polar and azimuthal angle(degree)"填写球坐标分量<img src="https://latex.codecogs.com/svg.image?\inline&space;\theta" title="\inline \theta" />, <img src="https://latex.codecogs.com/svg.image?\inline&space;\varphi" title="\inline \varphi" />。
8. 点击"Set Output folder"，设定输出文件夹，软件的计算结果都会保存在该文件夹内。
9. 在"Wave length"处输入实验所用X射线的波长。
10. 选择"Output expansion coefficients Slm(Q)"， "Output reconstructed S(Q)"和"Output G(r)"，来确认是否保存球谐系数<img src="https://latex.codecogs.com/svg.image?\inline&space;S_l^m(Q)" title="\inline S_l^m(Q)" />，重构的<img src="https://latex.codecogs.com/svg.image?\inline&space;(Q,S(Q))" title="\inline (Q,S(Q))" />和各向异性PDF<img src="https://latex.codecogs.com/svg.image?\inline&space;G(\vec{r})" title="\inline G(\vec{r})" />。
11. 点击"Calculate the selected"执行运算，可以在命令窗口观察到程序运行情况与报错信息。

![GUI2](https://github.com/worlddatong/Anisotropic-PDF/blob/main/imgs/6.png)![cmd1](https://github.com/worlddatong/Anisotropic-PDF/blob/main/imgs/8.png)

# Reference
1. Egami, Takeshi, and Simon JL Billinge. *Underneath the Bragg peaks: structural analysis of complex materials*. Elsevier, 2003.
2. Usher, Tedi-Marie, et al. "Electric-field-induced local and mesoscale structural changes in polycrystalline dielectrics and ferroelectrics." *Scientific reports* 5.1 (2015): 1-10.
3. Suzuki, Y., J. Haimovich, and T. Egami. "Bond-orientational anisotropy in metallic glasses observed by x-ray diffraction." *Physical Review B* 35.5 (1987): 2162.
4. Egami, T., et al. "Deformation induced bond orientational order in metallic glasses." *Journal of non-crystalline solids* 192 (1995): 591-594.

# Citation
If you find this project useful, please cite:
https://doi.org/10.48550/arXiv.2205.05865
