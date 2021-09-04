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

# 参考文献
1. Egami, Takeshi, and Simon JL Billinge. *Underneath the Bragg peaks: structural analysis of complex materials*. Elsevier, 2003.
2. Usher, Tedi-Marie, et al. "Electric-field-induced local and mesoscale structural changes in polycrystalline dielectrics and ferroelectrics." *Scientific reports* 5.1 (2015): 1-10.
3. Suzuki, Y., J. Haimovich, and T. Egami. "Bond-orientational anisotropy in metallic glasses observed by x-ray diffraction." *Physical Review B* 35.5 (1987): 2162.
4. Egami, T., et al. "Deformation induced bond orientational order in metallic glasses." *Journal of non-crystalline solids* 192 (1995): 591-594.

# 引用
如果Anisotropic PDF对您的研究有帮助，请引用这个网址：
https://github.com/worlddatong/Anisotropic-PDF
