# Python-
Python自动化办公常规操作代码
————提取美国证券分析报告中分析师的姓名电话和邮箱————
主要分为三步：

### Step1：信息提取
这一步的主要目的：按照电话或者邮箱将相应字段匹配出来并写入到txt文档中，减少冗余信息。
因为每个pdf的布局格式不一样，内容也不一致，可能出现以下几种情况：
#### *1.有些pdf没有邮箱，只有电话；
#### 2.有些pdf只有电话，没有邮箱；
#### 3.*有些pdf电话与邮箱都没有（但也是有统一的格式）。*
所以这里采用先进行页面分割匹配字段，按照左右页面切割，和上下页面切割两种方式进行切割提取信息（为了减少干扰信息，所以是分割页面后再匹配），将两种分割结果存储到两个不同的txt文档中（用于后续比对两种分割结果中的信息）

### Step2：信息校对
这一步的主要目的：对两种分割方式得到的结果进行比对，移动将信息较为完整的文档。
因为两种分割方式得到的结果会出现一下几种情况：
#### *1.匹配到的邮箱不完整
#### 2.匹配到的电话不完整
#### 3.匹配到的分析师姓名不完整*
所以通过比对邮箱的长度，电话的长度以及文件大小等多因素考量要选择保留的文档

### Step3：信息存储
这一步的主要目的：将分析师的姓名，电话，邮箱以及获取到的证书等信息存储到excel当中
这一步中最难的是关于分析师姓名的提取，因为观察到分析师姓名和邮箱都有很大相似程度，而且邮箱较为容易提取，所以通过比对分析师姓名和邮箱的方式来确定邮箱。（考量到还有一部分文档没有邮箱，主要可以分为两类：*1.相应信息的格式明确，容易提取；2.格式不明确，难提取。*对于格式明确的信息可以通过观察信息格式来进行匹配；而对于格式不明确的信息，暂时职能人工录入了~

第一个写的小项目，与大家共享~



