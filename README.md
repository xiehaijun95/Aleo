# Aleo
部署说明文档

一、硬件要求
The following are minimum requirements to run an Aleo node:
•	CPU: 16-cores (32-cores preferred)
•	RAM: 16GB of memory (32GB preferred)
•	Storage: 128GB of disk space
•	Network: 10 Mbps of upload and download bandwidth
二、Installation
	1、install Rust v1.65+
        curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
	2、cargo
		apt install cargo

	3、设置翻墙相关
	【git翻墙】
git config --global http.proxy http://14a5b2df9f993:313933a1d2@45.139.180.212:12323 
git config --global https.proxy https://14a5b2df9f993:313933a1d2@45.139.180.212:12323
【git取消翻墙】
git config --global --unset http.proxy && git config --global --unset https.proxy
【查看是否设置成功】
server@server:~/lotus$ cat ~/.gitconfig
[http]
        sslverify = false
        proxy = http://14a5b2df9f993:313933a1d2@45.139.180.212:12323
[https]
[https]
        proxy = https://14a5b2df9f993:313933a1d2@45.139.180.212:12323

4、设置代理
在https://www.ipaddress.com/ 中查询github.com和github.global-ssl.fastly.net两个域名的ip地址；
本地编辑host文件 sudo vim /etc/hosts；加入：
199.232.69.194 github.global-ssl.fastly.net
140.82.114.4 github.com
	5、源码安装aleo
		git clone https://github.com/AleoHQ/snarkOS.git --depth 1
cd snarkOS
./build_ubuntu.sh
cargo install --path .
	6、运行 ./run-prover.sh
 
三、加入Hpool
	1、官网下https://github.com/hpool-dev/aleo-miner/releases
	 
	2、在hpool获取API Key
		 
	3、运行proxy，并设置API Key
	 
	3、设置config.yaml
	 
	4、运行miner，
./miner-aleo-cuda-super
	 
四、加入AleoPool
	1、下载aleo-pool-prover
https://docs.aleopool.xyz/tutorial/alpha/pool-mode
	
2、開通礦池及新建賬戶
https://aleopool.xyz/#/miner/index
	 
3、运行aleo-pool-prover
進入 aleo-pool-prover 所在的目錄
./aleo-pool-prover_ubuntu_1804_gpu --account_name Deklod134 --miner_name Deklod134 -j 1
#確認程序包與下載的名字壹致
#修改「test_account」爲您的挖礦賬戶
#「test_miner」可自定義，用于網頁端設備的區分
-j 任務數（默認填寫1即可） -t 單個任務線程數量

4、查看算力及收益
 
