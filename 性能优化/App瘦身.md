#### 图片的瘦身

1. 找到无用的图片删除掉 (LSUnusedResources查找无用的图片) 

2. 压缩图片大小
   
   - 将图片压缩成webP格式，
  webp格式的优势：压缩率高，而且肉眼看不出来差异，同时支持有损压缩和无损压缩模式，有损模式 64%，无损模式 19%
   - 如何将图片压缩成WebP 
     用 谷歌公司提供的压缩工具，cwebp
     100 K 以上使用webp而 小于使用TinyPng进行压缩 ，
   
3. 改用webp格式或者svg
优点 ：图片体积小，经过伸缩也不会模糊
   
   > 因为改成webp格式的图片加载的时候会消耗更多的性能，所以选用svg，使用svg使用svgkit大概增加700k左右的包体积，如果减少的包大小没有这个库大小的话还是不要用，但是长期来看的话，还是用svgkit好一点，毕竟图片越来越多的



### 代码瘦身

app的安装包主要是由资源和可执行文件组成，所以，需要对可执行文件进行瘦身

可执行文件就是Mach-O文件，其大小就是有代码量决定的，**对可执行文件瘦身就是找到并删除无用代码的过程**

方法： 用appcode来做代码静态分析，在AppCode里选择 Code->Inspect Code 就可以进行静态分析