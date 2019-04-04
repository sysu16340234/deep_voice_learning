# Adam优化器
Adam 优化器结合了动量和RMSprop,权重更新方式如下：

![](https://www.zhihu.com/equation?tex=m_t%3D%5Cmu%2Am_%7Bt-1%7D%2B%281-%5Cmu%29%2Ag_t)

![](https://www.zhihu.com/equation?tex=n_t%3D%5Cnu%2An_%7Bt-1%7D%2B%281-%5Cnu%29%2Ag_t%5E2)

![](https://www.zhihu.com/equation?tex=%5Chat%7Bm_t%7D%3D%5Cfrac%7Bm_t%7D%7B1-%5Cmu%5Et%7D)

![](https://www.zhihu.com/equation?tex=%5Chat%7Bn_t%7D%3D%5Cfrac%7Bn_t%7D%7B1-%5Cnu%5Et%7D)

![](https://www.zhihu.com/equation?tex=%5CDelta%7B%5Ctheta_t%7D%3D-%5Cfrac%7B%5Chat%7Bm_t%7D%7D%7B%5Csqrt%7B%5Chat%7Bn_t%7D%7D%2B%5Cepsilon%7D%2A%5Ceta)
