## pip操作

- ### python第三方库官网

  https://pypi.org/

- ### pip清华源

  #### 临时使用

  ```
  pip install -i https://mirrors.tuna.tsinghua.edu.cn/pypi/web/simple some-package
  ```

  注意，`simple` 不能少。
  pip 要求使用 `https` ，因此需要 `https` 而不是 `http`

  #### 设为默认

  升级 pip 到最新的版本后进行配置：

  ```
  python -m pip install --upgrade pip
  pip config set global.index-url https://mirrors.tuna.tsinghua.edu.cn/pypi/web/simple
  ```

  如果您到 pip 默认源的网络连接较差，临时使用本镜像站来升级 pip：

  ```
  python -m pip install -i https://mirrors.tuna.tsinghua.edu.cn/pypi/web/simple --upgrade pip
  ```

  #### 配置多个镜像源

  如果您想配置多个镜像源平衡负载，可在已经替换 `index-url` 的情况下通过以下方式继续增加源站：

  ```
  pip config set global.extra-index-url "<url1> <url2>..."
  ```

- ### pip安装各种第三方库

  1. #### 直接联网安装

     ```
     pip install -r requirements.txt
     ```

  2. #### 批量下载，离线安装

     ##### 导出版本信息

     ```
     pip freeze > requirements.txt
     ```

     ##### 批量下载

     ```
     pip download -d DIR -r requirements.txt
     pip wheel -w DIR -r requirements.txt
     ```

     切记，不要在 windows 下载包，然后放到 Linux 上进行安装，这样八成装不上。

     经试验发现，download 适合补充wheel不可下载的包，两者搭配使用，才能将requirements文件的库完整的下载

     ##### 批量安装

     ```
     pip3 install --no-index --find-links=DIR -r requirements.txt
     ```

     