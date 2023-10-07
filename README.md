# docker-pure-ftpd
docker快速建立FTP

## 簡易說明

利用https://hub.docker.com/r/stilliard/pure-ftpd/

所提供的imges快速建立FTP可以限制只能取用那些資料夾

## 使用方法:

    git clone https://github.com/h63016401/docker-pure-ftpd.git

    cd docker-pure-ftpd

修改docker-compose.yml文件

其中第10行:C:/Users/Chihhao/Desktop/stable-diffusion-webui-docker改成自己想要給ftp使用的本機資料夾

在12行中21:21 port可以修改成自己想要映射的

    docker compose up

開另一個終端機進入容器:

    docker exec -it ftpd_server /bin/bash

新增FTP使用者跟密碼:

    pure-pw useradd kawsing -f /etc/pure-ftpd/passwd/pureftpd.passwd -m -u ftpuser -d /home/ftpusers/kawsing

以上範例的使用者為:kawsing
連接到的預設目錄為:/home/ftpusers/kawsing

## 最大客戶數

預設情況下，一次設定 5 個最大客戶端，但可以透過使用以下環境的數量來增加此設置，例如，然後還增加從開放的公共連接埠的數量。還需要在執行FTP_MAX_CLIENTSdocker FTP_MAX_CLIENTS=50runFTP_PASSIVE_PORTS=30000:30009 FTP_PASSIVE_PORTS=30000:30099時開啟這些連接埠。此外，可以透過設定環境變數來指定每個ip的最大連線數FTP_MAX_CONNECTIONS。預設值為5。

## 使用 filezilla 測試

![Alt text](test.png)


