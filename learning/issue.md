# 脚本执行被阻止

cnpm : 无法加载文件 C:\Users\yxls0\AppData\Roaming\npm\cnpm.ps1，因为在此系统上禁止运行脚本。有关详细信息，请参阅 https:/go.microsoft.com/fwlink/?LinkID=135170 中的 about_E 
xecution_Policies。
所在位置 行:1 字符: 1

解决方法：
1、win+x 打开PowerShell（管理员）
2、set-ExecutionPolicy RemoteSigned //设置为打开
3、键入Y或者A,同意
4、执行get-executionpolicy查看是否更改成功，为RemoteSigned表示成功

# image-webpack-loader build失败

 ERROR  Failed to compile with 2 errors                                                                                                                              22:29:17
 error  in ./src/assets/logo.png

Syntax Error: Error: 'E:\learning\vue\v2cli4\node_modules\pngquant-bin\vendor\pngquant.exe' �����ڲ����ⲿ���Ҳ���ǿ����еĳ���
���������ļ���

原因：
  image-webpack-loader安装不全，家里环境安装时可能存在依赖安装不全的问题。
解决方案：
  重新安装image-webpack-loader，
  npm uninstall image-webpack-loader 
  cnpm install --save-dev  image-webpack-loader 