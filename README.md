# Windows_Scan
此工具主要利用yara规则扫描主机恶意进程和文件，主要分为以下功能，

1、对进程进行扫描，根据yara规则匹配恶意进程，并输出进程基本信息，包括：PID、PPID、父进程、网络连接、可执行文件路径、进程创建时间、匹配规则；

2、对进行文件扫描，根据yara规则匹配恶意文件，并输出文件基本信息，包括：文件名、文件MD5、文件路径、修改时间、创建时间、匹配规则；

3、计算文件MD5，并根据MD5值，检索主机上是否还存在相同文件；

### 说明：

1、程序中已经内置64条规则，规则来源均为：https://github.com/m-sec-org/d-eyes/tree/master/yaraRules

2、由于作者使用Go的版本比较高，因此导致win2008和win7 及之前的windows版本无法运行，目前测试，最低支持win server2012

3、由于工具本省内置大量规则，导致火绒、360等杀毒软件均会报毒，使用前 请确认MD5值是否相同；

免责声明：此工具仅限于安全研究，用户承担因使用此工具而导致的所有法律和相关责任！作者不承担任何法律责任

## 工具运行界面
![image](https://github.com/user-attachments/assets/a809e82c-0a35-4e5d-9151-27b59137a028)


## 功能
### 进程扫描
1、默认扫描全部进程，也可以输入指定进程进行扫描；

2、由于担心扫描过程会影响主机正常业务和提高扫描效率，因此可设置不扫描内存占用大的进程，这个必须要填写，不填写则不会扫描所有进程；

3、可以指定规则库进行扫描，internal只使用内置规则、external只使用自定义规则、both两个规则一起用，也会出现两个输出表格；使用external和both都需要指定外挂规则库的路径；
![image](https://github.com/user-attachments/assets/bb05fcb0-bc55-4504-b6ac-df729293de2d)
![image](https://github.com/user-attachments/assets/a73f2798-c3f7-4727-8d70-86f32492e2b2)


### 文件扫描
1、指定目录进行扫描，会递归扫描目录下面的所有类型文件；

2、扫描模式跟上面进程扫描模式一样，不在赘述；
![image](https://github.com/user-attachments/assets/0913ac19-d2d0-4b3d-930c-3a7ebf55da50)
![image](https://github.com/user-attachments/assets/3d575394-8445-4fb9-b5de-593be2087733)



### MD5计算及查找
1、计算指定文件的MD5值；

2、根据MD5值，在指定目录查找是否存在相同文件；
![image](https://github.com/user-attachments/assets/d66efd47-602a-4ea5-913c-45dabe757d19)

### 使用外挂规则进行扫描
1、扫描模式选择：external

2、输入规则路径

![image](https://github.com/user-attachments/assets/db1c4401-7fea-4a9c-9d5a-2e7c9d669ea3)



