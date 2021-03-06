# 清涟-让校园网更稳定  
由琴梨梨开发的校园网登录器，目前仅支持南京中医药大学  

## 构建方法  
1. 克隆本仓库到本地  
2. （可选）把本仓库zip打包为package.nw  
3. 下载适用于你的操作系统的nw.js  
4. 把nw.js解压到项目文件夹  
5. 运行nw即可使用  

## 贡献代码  
如果你针对南京中医药大学，请直接提交pr  
如果你想适配更多学校，请自行fork本仓库并按照许可内容进行二次开发  
适配其他学校的项目请自行在fork后修改项目名称为学校名+Elina格式  

## 我不是南中医的，我该怎么移植？  
1. 如果你的学校使用Web登录，直接把登录页面的请求JS复制过来稍作修改替换tryLogin方法  
2. 根据系统的不同，你可能需要添加或删除一些输入框  
3. 你不用担心发生CORS错误，nw.js不会发生CORS  
4. 部分学校尤其是境外学校可能无法正常使用MIUI的204检测地址，你可以替换为高通的或者谷歌的  
5. 清涟不支持PPPoE认证，但你可以把路由器的PPPoE设置页面API设置为清涟的请求地址来间接使用清涟  

## 简单的FAQ

#### 为什么叫清涟？  
清涟其实就是轻连的谐音啦！  
无意间想到的名字而已，觉得很合适就保留了  

#### 使用清涟是否会被学校发现？  
清涟发起的登录请求和正常认证的请求完全一致，所以非常安全  

#### 清涟会影响设备性能或续航吗？  
在surface go上，清涟在后台以500ms检测频率运行时，CPU使用率小于0.5%，对续航时间的影响只有不到0.5%甚至0.4%  
当清涟仅仅停留在后台而不工作时，CPU使用率小于0.05%  
但倘若设备没有一个兼容Chromium硬件加速的GPU或通过附加指令禁用了硬件加速，清涟可能消耗更多的CPU用于渲染页面.你可以通过任务管理器寻找是否有gpu-process进程来判断清涟是否在硬件加速模式下,如果清涟没有默认开启硬件加速,你可以使用--ignore-gpu-blacklist指令启动清涟来尝试修正这个问题    

#### 为什么我的电脑上运行清涟没有字？  
你可能全局安装了基于LLVM的DX Compiler，Chromium系程序目前无法兼容，请参考[这个Issue](https://github.com/microsoft/DirectXShaderCompiler/issues/3527)  

#### 清涟的界面不是很好看？  
你的感觉是对的。琴梨梨没有任何艺术细胞，UI从来就没做的好看过。你可以把你想要的设计作为PR提交，琴梨梨觉得好看就会合并的  
背景图也是可以自定义的，你可以自己替换自己想要的背景图（但如果你有优质的涩图，请务必发琴梨梨一份）  

#### 清涟导致了并发上限？  
请把针对校园网的随机MAC地址关掉  

