mkdocs

[主要参考教程](https://blog.csdn.net/qq_41261251/article/details/116021097)


# bash 操作
* 创建新站点
```bash
mkdocs new dir_name
```
*dir_name为站点的名字，可以自己命名*

* 在站点目录下生成site文件夹
```bash
mkdocs build
```

* 访问本地站点
```bash
mkdocs serve
```

# YAML文档配置
```YAML
site_name: ZX's MkDocs
repo_url: https://gitee.com/rano-zink/mymkdocs/
repo_name: /mymkdocs/
edit_uri: ""
site_description: 
copyright: Copyright &copy; 2023 - 2024 zhaoxin

theme: readthedocs
nav:
  - Home: index.md
  - 项目:
    - 行波马达:
      - SPI: project/行波马达/SPI.md
      - 控制: project/行波马达/马达控制.md
    - 微镜:
      - 滑膜控制: project/微镜/滑膜控制.md
  - Wiki:
    - 编程:
      - CPP:
        - ch1: project/cpp/01demo.md
        - ch2: project/cpp/CPPoutline.md
    #   - python: 不可以出现空目录 nav下的目录最后一级必须指向具体的文档
    # - 电路:
    # - FPGA:
    # - 深度学习:
    # - 控制算法:
    # - 论文写作:
    - 操作系统: project/操作系统/OS.md
```
* 同一级目录的缩进应保持一致
* nav 不可以出现空目录 nav下的目录最后一级必须指向具体的文档
* 目录下的文件要与文件夹中保持一致，如果文件在文件夹中却不在目录下，可能会报错



# github
* 建立远程仓库并与mkdocs站点进行连接
```
git init
git remote add origin2 https://github.com/rano-zink/ZhaoXin_project.git
```

* 
方法一：手动部署
将 site 目录下的所有文件复制到一个新的分支（通常是 gh-pages）。
```bash
git checkout -b gh-pages
cp -r site/* .
git add .
git commit -m "Deploy documentation"
git push origin2 gh-pages
```
在 GitHub 仓库的设置页面中，找到 “GitHub Pages” 部分，将 “Source” 设置为 gh-pages 分支，然后点击 “Save”。稍等片刻，你的文档就会部署到 https://<your-github-username>.github.io/<your-repo-name> 上。
[mydocs](https://rano-zink.github.io/ZhaoXin_project/)

* 
方法二：使用 mkdocs gh-deploy 命令
运行以下命令，MkDocs 会自动将构建好的文档推送到 gh-pages 分支：
``` bash
mkdocs gh-deploy
```
之后，在 GitHub 仓库的设置页面中确认 “GitHub Pages” 的源分支为 gh-pages。
完成上述步骤后，你就可以通过 https://<your-github-username>.github.io/<your-repo-name> 访问部署好的 MkDocs 文档了。








