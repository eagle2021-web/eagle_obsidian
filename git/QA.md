Q: fatal: unable to access 'https://github.com/eagle2021-web/eagle_obsidian/': error setting certificate verify locations:  CAfile: E:/sdk/Git/mingw64/etc/ssl/certs/ca-bundle.crt CApath: none
A: git config --global http.sslCAInfo "C:/sdk/Git/mingw64/etc/ssl/certs/ca-bundle.crt"

