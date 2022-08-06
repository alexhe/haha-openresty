# haha-openresty

## 编译参考
https://gist.github.com/c9n/b31d3ad9314ad923699e

## 下载依赖包:
openssl-1.1.1k.tar.gz
https://www.openssl.org/source/
https://www.openssl.org/source/openssl-1.1.1k.tar.gz

./configure --with-openssl=/xxx/.../3rd/openssl-1.1.1k/


## Mac编译 v1.21.4.1说明


* brew install pcre openssl 安装的openssl v3版本不能直接使用,回退到v1.1.1q
* 下载依赖包:https://www.openssl.org/source/openssl-1.1.1q.tar.gz
* openssl v1.1.1q 有隐式函数调用错误，Werror导致， 已经修改v3ext.c 添加头文件 #include <string.h> 解决
* 配置目标产物install到项目dist/目录: ./configure  --prefix=/Users/xxx/work/code/github/haha-openresty/openresty-1.21.4.1/dist  --with-openssl=../3rd/openssl-1.1.1q/
* make -j8 根据cpu核数设置-j参数
* make install 安装到 dist/目录