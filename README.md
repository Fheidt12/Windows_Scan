# Windows_Scan
此工具主要利用yara规则扫描主机恶意进程和文件，主要分为以下功能，

1、对进程进行扫描，根据yara规则匹配恶意进程，并输出进程基本信息，包括：PID、PPID、父进程、网络连接、可执行文件路径、进程创建时间、匹配规则；

2、对进行文件扫描，根据yara规则匹配恶意文件，并输出文件基本信息，包括：文件名、文件MD5、文件路径、修改时间、创建时间、匹配规则；

3、计算文件MD5，并根据MD5值，检索主机上是否还存在相同文件；

### 说明：

1、程序中已经内置64条规则，规则来源均为：https://github.com/m-sec-org/d-eyes/tree/master/yaraRules

2、由于作者使用Go的版本比较高，因此导致win2008和win7 及之前的windows版本无法运行，目前测试，最低支持win server2012

免责声明：此工具仅限于安全研究，用户承担因使用此工具而导致的所有法律和相关责任！作者不承担任何法律责任

## 工具运行界面
![image](https://github.com/user-attachments/assets/d154c6cb-39cb-44b4-a21e-42de39204c42)

## 功能
### 进程扫描
1、默认扫描全部进程，也可以输入指定进程进行扫描；

2、由于担心扫描过程会影响主机正常业务和提高扫描效率，因此可设置不扫描内存占用大的进程，这个必须要填写，不填写则不会扫描所有进程；

3、可以指定规则库进行扫描，internal只使用内置规则、external只使用自定义规则、both两个规则一起用，也会出现两个输出表格；使用external和both都需要指定外挂规则库的路径；
![d53993faef51ebcb04034fee9853898](https://github.com/user-attachments/assets/64ac6a34-d503-4b70-9bb4-89e2ef50788c)
![80fb0f6732e9aa4bfb32865f2ee62c7](https://github.com/user-attachments/assets/bd5264e7-1ce6-469d-b37d-d6772ef9e861)

### 文件扫描
1、指定目录进行扫描，会递归扫描目录下面的所有类型文件；

2、扫描模式跟上面进程扫描模式一样，不在赘述；
![01590c0585eaddf636e23a6a16624f2](https://github.com/user-attachments/assets/aad1c82f-2c0f-44b6-84f1-003df00973ed)
![64f3aee570d7cde657875db3bd594bf](https://github.com/user-attachments/assets/a640baeb-3d07-4a47-8eb1-12276441f91c)

### MD5计算及查找
1、计算指定文件的MD5值；

2、根据MD5值，在指定目录查找是否存在相同文件；
![efbd5f3e015018fc75cbfe7e22a9cd1](https://github.com/user-attachments/assets/1b262506-7086-4834-b33b-0a17aa05e64a)



