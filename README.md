# Missing-file-libarclite_iphoneos.a
Missing file libarclite_iphoneos.a 

## 本仓库已经命令行arc里面有文件库 下载即可
# 具体步骤


跳转到存放文件的目录
cd /Applications/Xcode.app/Contents/Developer/Toolchains/XcodeDefault.xctoolchain/usr/lib/
创建arc目录
#执行第一个命令后需要输入Mac用户的登录密码以获取root权限
sudo mkdir arc
cd  arc
下拉文件资源
#命令的最后一个点不能遗漏，这是git clone后的解压目录（当前目录），否则创建目录/Libarclite-Files
sudo git clone https://github.com/kamyarelyasi/Libarclite-Files.git .
修改访问权限
sudo chmod +x *
修改编译脚本文件
文件目录：
原生App：Pods\Target Support Files\Pods-App\Pods-App-frameworks.sh
Flutter App：Pods\Target Support Files\Pods-Runner\Pods-Runner-frameworks.sh

搜索（CMD+F）：source="$(readlink "${source}")"
替换成：source="$(readlink -f "${source}")"
修改编译脚本
修改完成，编译（Cmd+B）或执行（Cmd+R）程序
