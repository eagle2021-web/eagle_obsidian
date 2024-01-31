## hosts文件权限
hosts右键->安全->编辑->写入
## github ip查询
```text
https://www.ipaddress.com/site/github.com  github
https://ipaddress.com/analysis/github.global.ssl.fastly.net+github.com 证书
```
## hosts文件配置
```text
140.82.112.3 github.com
151.101.1.194 github.global.ssl.fastly.net
```
## git仓库初始化
```shell
echo "# eagle_python" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/eagle2021-web/eagle_python.git
git push -u origin main
```

## 设置和取消

1）git config --global url."https://ghproxy.com/https://github.com".insteadOf "https://github.com" 这个设置后怎么取消

要取消之前通过 `git config --global` 设置的 `https://github.com` 到 `https://ghproxy.com/https://github.com` 的 URL 替换规则，你需要运行以下命令来移除相应的配置：

```
git config --global --unset url."https://ghproxy.com/https://github.com".insteadOf
```

这条命令会从全局配置中移除你所设置的 `insteadOf` 规则。如果你想验证是否成功移除了相应的配置，可以使用以下的 `git config` 命令来列出所有相关的配置：

```
git config --global --get-regexp url.*
```

如果执行该命令后，没有列出类似的 URL 替换规则，那表示你的替换设置已经被成功取消。

还要注意，如果在取消配置时遇到任何错误，确保你已经准确地输入了完整的替换 URL。任何的拼写错误或遗漏都可能阻止 Git 识别出你想要移除的配置项。
2）git config --global url."https://hub.fastgit.xyz/".insteadOf "https://github.com/"设置后如何取消
在 Git 中，如果你已经使用 `git config --global` 设置了 URL 替换规则，可以通过删除相应的配置来取消这个设置。使用以下命令可以删除对应的 URL 替换规则：

```
git config --global --unset url."https://hub.fastgit.xyz/".insteadOf
```

这会从全局的 Git 配置中移除你之前设置的 `"https://github.com/"` 替换为 `"https://hub.fastgit.xyz/"` 的规则。如果你想查看当前的配置，以确认规则是否已经被正确移除，你可以使用下面的命令：

```
git config --global --get-regexp url.*
```

这将列出所有的全局 URL 替换规则配置。如果你之前设置的替换规则已经不存在了，则代表你成功取消了该设置。

### 取消代理
	1.
	    取消http代理
    
		git config --global --unset http.proxy
    

		git config --global --unset url."https://gitclone.com/.insteadof ".insteadOf
    
	2 
		取消https代理
		git config --global --unset https.proxy