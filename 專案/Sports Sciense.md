## Sports Sciense

參考了交大彭文志教授的論文：  
ICDM'21: Exploring the Long Short-Term Dependencies to Infer Shot Influence in Badminton Matches  

並且改寫成排球的模式  
由於排球在每一回合中，一方都有三次的控球權，因此還會需要先用LSTM layer學習出一個round embedding(名稱暫定)  
再利用上面論文的方法透過CNN與GRU layer的結合來獲取長短期之間的information  
比較困難的點在於，因為我們的資料是沒有太多空間資訊的，目前有的只有擊球者的位置。這個部分可能還要跟對方討論是否可以增加更多的資訊，但對方其實也有提到過說，因為他們是利用人工的方式看影片來作標註，像排球這種多人運動，其實有蠻多攝影機死角，是無法拍到所有場上人員的位置的，這也是一大難題  
只能先利用目前既有的資料去作嘗試  
  
另一個困難點是資料處理上真的很麻煩...  
因為我們收到的資料，他是用excel檔，並用不同顏色的空格來標註是對手發球 or 對手回擊，並且他是將兩方的行動分開記錄在兩個不同的excel檔案中  
需要先處理合併的問題  
