## 1. 通过 axel 加速

``` shell
# 修改配置文件 /etc/makepkg.conf
# 修改如下内容：
DLAGENTS=('file::/usr/bin/curl -gqC - -o %o %u'
          'ftp::/usr/bin/curl -gqfC - --ftp-pasv --retry 3 --retry-delay 3 -o %o %u'
          'http::/usr/bin/curl -gqb "" -fLC - --retry 3 --retry-delay 3 -o %o %u'
          'https::/usr/bin/curl -gqb "" -fLC - --retry 3 --retry-delay 3 -o %o %u'
          'rsync::/usr/bin/rsync --no-motd -z %u %o'
          'scp::/usr/bin/scp -C %u %o')
# 修改为：
DLAGENTS=('file::/usr/bin/curl -gqC - -o %o %u'
          'ftp::/usr/bin/axel -n 15 -a -o %o %u'
          'http::/usr/bin/axel -n 15 -a -o %o %u'
          'https::/usr/bin/axel -n 15 -a -o %o %u'
          'rsync::/usr/bin/rsync --no-motd -z %u %o'
          'scp::/usr/bin/scp -C %u %o')   
```

## github 拉取加速

``` shell
# 通过镜像源加速
# https://gitclone.com/github.com    https://ghproxy.com
url.https://ghproxy.com/https://github.insteadof=https://github
```
