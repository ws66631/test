# CUDA

## 1、查看显卡

```
控制台输入 nvidia-smi 查看支持的CUDA版本 
```

## 2、安装vs studio

## 3、安装显卡驱动

```
显卡驱动下载地址
https://www.nvidia.cn/geforce/drivers/
```

## 4、安装cuda

```
cuda下载地址
https://developer.nvidia.com/cuda-toolkit-archive
```

## 5、安装cudnn

```
cudnn下载地址|下载时cuda的版本要和cudnn的版本对应
https://developer.nvidia.com/cudnn-archive

cuda安装成功后把cudnn压缩包解压，把所有文件复制到cuda安装目录下，完成之后配置环境变量，需要添加\include \bin \lib \libnvvp
接着输入nvcc -V  显示cuda版本则为安装成功
```



# Python

```
python下载地址
https://www.python.org/downloads/
```



# Conda

```
conda下载地址
https://www.anaconda.com/download

conda命令
	conda create -n env_name python=3.9	创建虚拟环境
	conda activate env_name	进入虚拟环境
	conda list 查看conda包

添加镜像源
    conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
    conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main/
    conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/conda-forge/
    conda config --add channels https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/bioconda/
    conda config --add channels https://mirrors.bfsu.edu.cn/anaconda/cloud/bioconda/
    conda config --add channels https://mirrors.bfsu.edu.cn/anaconda/cloud/conda-forge/
    conda config --add channels https://mirrors.bfsu.edu.cn/anaconda/pkgs/free/
    conda config --add channels https://mirrors.bfsu.edu.cn/anaconda/pkgs/main/

下面这个我没用过, 可以添加一下试试看.
    conda config --add channels https://mirrors.bfsu.edu.cn/anaconda/pkgs/r/

目前国内提供conda镜像的大学
	清华大学: https://mirrors.tuna.tsinghua.edu.cn/help/anaconda/
	北京外国语大学: https://mirrors.bfsu.edu.cn/help/anaconda/
	南京邮电大学: https://mirrors.njupt.edu.cn/
	南京大学: http://mirrors.nju.edu.cn/
	重庆邮电大学: http://mirror.cqupt.edu.cn/
	上海交通大学: https://mirror.sjtu.edu.cn/
	哈尔滨工业大学: http://mirrors.hit.edu.cn/#/home
	(目测哈工大的镜像同步的是最勤最新的)

```

# pytorch

```
pytorch官网地址  https://pytorch.org/

pytorch安装指示页面  https://pytorch.org/get-started/locally/

pytorch的安装需要根据cuda的版本来进行
	cuda11.8  pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
	cuda12.6  pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu126
	cuda12.8  pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu128

在安装时如果发现下载的pytorch包小于1GB，那么这个包大概率不是GPU版本的，而是CPU版本的，这种情况下可以指定版本为GPU版，如
torch===2.0.0+cu118
```



# JDK

```
https://blog.csdn.net/m0_70545163/article/details/141332829
```



# Maven

```
Maven最新版下载地址
	https://maven.apache.org/download.cgi
Maven历史版本下载地址
	https://archive.apache.org/dist/maven/maven-3/
	
 下载完成后解压，接着在解压的目录下插件一个	repository	目录当作Maven的仓库
 接着配置环境变量
 变量名：MAVEN_HOME
 变量值：D:\Programming\Apache\Maven\apache-maven-3.8.6
     //此处的变量值为你存放Maven的解压路径
 变量名：M2_HOME
 变量值：D:\Programming\Apache\Maven\apache-maven-3.8.6\repository
     //此处的变量值为你存放Maven的解压后目录中的文件夹的路径
     //很多自动依赖的系统，如springboot、springcloud引用了该地址，建议配置上
 %MAVEN_HOME%\bin
 
 配置完环境变量输入mvn -v即可查看版本和路径
```

上面的步骤完成之后就开始编辑配置文件

```xml
配置文件的路径是/conf/settings.xml
需要添加阿里云仓库,<mirrors></mirrors>标签中添加 mirror 子节点
	<!-- 阿里云仓库 -->
    <mirror>
      <id>alimaven</id>
      <mirrorOf>central</mirrorOf>
      <name>aliyun maven</name>
      <url>http://maven.aliyun.com/nexus/content/repositories/central/</url>
    </mirror>

接下来需要配置JDK，在文件找到profiles节点，添加如下配置
    <!-- java版本 --> 
    <profile>
          <id>jdk-1.8</id>
          <activation>
              <activeByDefault>true</activeByDefault>
              <jdk>1.8</jdk>
          </activation>
 
          <properties>
              <maven.compiler.source>1.8</maven.compiler.source>
              <maven.compiler.target>1.8</maven.compiler.target>
              <maven.compiler.compilerVersion>1.8</maven.compiler.compilerVersion>
          </properties>
    </profile>

接着就是配置本地仓库的路径，在localRepository节点中配置
<localRepository>D:\Programming\Apache\Maven\apache-maven-3.8.6\repository</localRepository>


```

# unity

```
Unity Hub下载地址
https://unity.cn/releases
```

# C++

```
gcc --version
g++ --version
gdb --version
```

# npm

```
查看配置
npm config get
设置配置
npm config set registry ...
npm config set prefix C:\User\npm\global
设置缓存地址
npm config set cache C:\User\npm\cache
更换镜像源
npm config set registry https://registry.npmmirror.com
```

# node

```
下载地址
https://nodejs.org/zh-cn/download
```

# vue

```
安装vue
npm install -g @vue/cli

vue2.0的安装：vue init webpack 项目名 
vue3.0的安装：vue create 3.0project项目名 ； ( 项目名不要取中文和大写字母。)
```

