# Introduction
this repo is a clash configration for **Linux** (ubuntu) without GUI
## file description
* zip is a personal configration which is no use for others, even you can delete it
* clash is a binary executable file 
  * download from https://github.com/Dreamacro/clash/releases
* Country.mmdb is needed by clash
* config.yaml is needed by clash
  * you can obtain this file from your Service Provider

# how to use
```bash
git clone https://github.com/wing-anemone/clash ~/clash
# wget url to get config.yaml and put it in clash directory 
# -d to set config directory
nohup ~/clash/clash -d ~/clash > /dev/null 2>&1 &!
export http_proxy=http://127.0.0.1:7890; export https_proxy=$http_proxy;
```
# modify parameters by web (if you want)

```bash
cd ~/clash
git clone https://github.com/Dreamacro/clash-dashboard
git checkout -b gh-pages origin/gh-pages && git pull
vim config.yaml
```

you need add this to config.yaml 
* position is between log-level and proxies
* you must have setret line
```bash
external-controller: ":8888"
external-ui: clash-dashboard # clash-dashboard的路径
setret: '12345'
```
restart your clash, and you can view it in url:

ip:8888/ui

if it works, you will see a gui which you need input your ip, port and password


