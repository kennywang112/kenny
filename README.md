# kenny
## linux
### 壓縮檔案
>1.備份資料的時候方便整理.  
>2.將檔案變小，節省電腦硬碟的空間。(但圖片、音訊、視訊等多媒體檔案壓縮率低，並不能有效節省空間).  
>3.將無數個散亂的檔案打包成一個較小的檔案，亦方便資訊在網路上流通。(可將永久免費版之付費軟體輕鬆分享).  
>4.壓縮檔案時，可以視情況進行加密.   
### 各壓縮差別
#### 考慮因素
>1.壓縮率（compression ratio，能夠將檔案壓到多小.  
>2.解壓縮所需的時間，也就是需要的 CPU 計算量.   
>3.解壓縮所需的記憶體空間.   
>4.相容性（compatibility，即解壓縮程式的普遍性，是不是大部分人都有辦法解壓縮這種格式？

### 檔案搜尋
> find [path] [option] [action] filename
> which filename
### 檔案內容查閱
>more一頁一頁的顯示 檔案內容
>less與more 類似 ，顯示 檔案室允許用戶既可以 向前又可以 向後翻頁閱讀檔案
>head 取出前面幾行(預設10行)
>tail 取出後面幾行(預設10行).  
### 資料傳輸
#### 溝通案例：小美開瀏覽器(客戶端)並輸入Youtube首頁網址(伺服器端)
>1.瀏覽器(客戶端)向YouTube的遠端主機(伺服器端)發出一個請求.   
>2.該請求透過網路被傳遞到YouTube首頁的位址.   
>3.位於YouTube首頁的遠端主機(伺服器端)收到一個請求.  
>4.遠端主機(伺服器端)會根據請求內容，找到一個對應的網路資源.   
>5.取出對應的網路資源，伺服器將其回傳至小美的瀏覽器.  
>6.瀏覽器(客戶端)收到回傳內容，開始解析資源，顯示於瀏覽器上
#### Port
>通訊埠號是TCP/UDP與上層通訊的通道，當TCP/UDP要傳送訊息時，會指定要由哪一個通訊埠號來接收。一些常用的服務會使用特定的埠號來等待要求的訊息。埠號是由16個位元所組成的號碼，0 ~ 255 為保留號碼，256~65535則可自行設定
#### TCP/IP
>TCP/IP提供了點對點的連結機制，將資料應該如何封裝、定址、傳輸、路由以及在目的地如何接收，都加以標準化。它將軟體通信過程抽象化為四個抽象層，採取協議堆疊的方式，分別實作出不同通信協定。協定套組下的各種協議，依其功能不同，被分別歸屬到這四個階層之中，常被視為是簡化的七層OSI模型
#### 當瀏覽器輸入網址，發出一個GET請求時,過程中發生了哪些事情
>1.TCP三向交握.   
>在瀏覽器送出請求之後，瀏覽器和伺服器就會開始初步溝通，確定雙方的溝通管道順暢，以便後續請求的執行.  
>2.瀏覽器請求、資料傳輸、渲染畫面.   
>如同前面所提，當三項交握結束後，瀏覽器和伺服器便會開始執行請求、資料傳輸與渲染畫面的過程.   
>3.TCP四次揮手，結束連線.  
>在網頁成功渲染之後，瀏覽器就會和伺服器進行最後的溝通，確認傳輸過程已完成，準備結束連線. 
### 網路相關
#### route
>add:新增一條路由規則.   
>del:刪除一條路由規則.   
>-net:目的地址是一個網路. 
>-host:目的地址是一個主機.  
>target:目的網路或主機.   
>netmask:目的地址的網路掩碼.  
>gw:路由資料包通過的閘道器.   
>dev:為路由指定的網路介面
#### ping
##### 常用網路檢測工具，可藉由發送ICMP ECHO_REQUEST封包，檢查自己與特定設備之間的網路是否暢通，並同時測量網路連線的來回通訊延遲時間（round-trip delay time）
>-n：參數指定封包數→EX：ping -n 10 blog.gtwang.org.  
>-t：持續監看網路是否正常→EX：ping -t blog.gtwang.org.  
>-4 /-6：IPv4 /IPv6.   
>-c：指定Ping次數→EX：ping -c 4 blog.gtwang.org.  
>-s：指定發送 的數據字結 數→EX：ping -s 1024 facebook.com.   
> -i：指定收發 資訊間隔時間→EX：ping -i 0.4 facebook.com
#### 影響網路速度的因素
>延遲（Latency）：封包從來源端至目的端中間所花的時間.   
>頻寬（Bandwidth）：傳輸媒介的最大吞量
#### 網路延遲（Latency）的組成元素
>1.propagation delay：封包在網路線上傳輸所花費的時間，與網路線上電子訊號跑的速度有關，這個時間就是距離除以訊號傳送速度所得到的數值.  
>2.transmission delay：網路卡將資料傳送到網路線上所花的時間，與網路設備的傳送速度有關.  
>3.nodal processing delay：路由器處理封包表頭、檢查位元資料錯誤與尋找 配送路徑等所花費的時間.  
>4.queuing delay：路由器因為某些因素無法立刻將封包傳送到網路上，造成封包暫存在佇列中等待的時間
#### netstat
>查看端口是否被占用：netstat -al grep 3306.   
>查看數據包統計信息：netstat -s.  
>查看路由信息：netstat -r
