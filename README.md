# 个人底层库
白嫖了这么多开源代码，把自己用的一些底层代码开源，随缘维护  
</br>

代码有日志类  
核心诉求是简化操作，现有的glog体系一般要初始化，觉得太过麻烦了就自己改了一版
```
LG<<"some log";
FT_IF(2>1)<<"some info";
LG_FT<<"some error info";
```
</br>


串行化类  
可以把数组快速转成字符串或者文件，或者json 
```
struct SomeData
{
  int a;
  double b;
  std::string str;
};
ZM_BF_SUPPORT_3(SomeData, a, b, str);


```

文件类  
一些文件处理的快速操作，枚举子文件夹，创建文件等
```
EnsureFile(makeSubPath("code","sub_code"));
```
</br>


随机数类  
```
uniform_real<double>(0,1);
if(rate_random(0.2)){
}

```

pytorch c++ 比较完整的一些底层库(感觉全网用c++版pytorch的好少)  
```
TMat tm = createTMat<float>({1,2}, {0.2,0.3}, tr::KF32);
DyAcc acc(tm);
float v01 = acc._get<float>(0,1);

MultiDenseLayer net({2,3,4}, md_relu, md_so_mx);

```

