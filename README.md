## 喂投式claim POAP js脚本

1. 安装node和git，要求nodejs版本不低于12.16.0

2. 从github上复制代码

  ```
  git clone git@github.com:waxcloud2021/poap.git
  ```

3. 安装运行脚本需要的依赖包

  ```
  npm install
  ```

4. 配置好你使用代理的端口号（科学上网）

  ```
  proxy: "http://127.0.0.1:7890",
  ```

  端口号7890按实际修改

5. 如果你没有使用代理，跳过第4步，代码中做一下切换(两处)

  ```
  require("request").get(options, function (error, response, body) {
  // requestProxy.get(options, function (error, response, body) {
  ```

  ```
  require("request").post(options, function (error, response, body) {
  // requestProxy.post(options, function (error, response, body) {
  ```

6. 编辑address_list.txt文件

  ```
  eth1:0xdeaddeaddeaddeaddeaddeaddeaddeaddeaddead
  eth2:0xdeaddeaddeaddeaddeaddeaddeaddeaddeaddead
  eth3:0xdeaddeaddeaddeaddeaddeaddeaddeaddeaddead
  4:0xdeaddeaddeaddeaddeaddeaddeaddeaddeaddead
  5:0xdeaddeaddeaddeaddeaddeaddeaddeaddeaddead
  6:0xdeaddeaddeaddeaddeaddeaddeaddeaddeaddead
  7:0xdeaddeaddeaddeaddeaddeaddeaddeaddeaddead
  8:0xdeaddeaddeaddeaddeaddeaddeaddeaddeaddead
  9:0xdeaddeaddeaddeaddeaddeaddeaddeaddeaddead
  10:0xdeaddeaddeaddeaddeaddeaddeaddeaddeaddead
  ......
  ```

  冒号的左边是你为钱包地址起的别名，也可以是序号，随意命名，不要有冒号；右边是你的钱包地址，请确保地址正确. 编辑好后保存


7. 通过POAP-bot或https://poap.website/xxxxxxxxxx 得到claim POAP的6位code(qr_hash)或是带有code的URL以后，如下运行脚本(xxxxxx替换为真实code)

  ```
  node claim xxxxxx 4
  ```
  或
  ```
  node claim http://poap.xyz/claim/xxxxxx 4
  ```

  便把POAP claim到了别名为 4 的地址里

