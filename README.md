# 設置重點提示
在專案的appsettings.json 中，在JWT 中的KEY 宣告自己的KEY種子
![1](images/1_appsettings_1.png?width=907&height=550)

# 驗證方式
-  使用**POSTMAN**工具，在**POST** 的 **Body**頁籤中，將正確的 username及password 使用JASON 方式輸入 
-  送出後，收到500錯誤。提示種子至少要256 bit，我們只有160 bit (20個字)
![4](images/2_send_post.png)


- 我們加字，再重新執行程式。再用POSTMAN 重新發送請求，程式比對username 及  password 都正確，就會返回 JWT Token
![2](images/1_appsettings_2.png)

**JWT Token** 就是下圖綠色圈起來的文字
![6](images/3_response_token.png)

- 接下來，我們要確認**驗證**是否發揮作用。程式裡宣告要訪問 **/secure** 這個路徑是必須經過授權的，於是我們用**GET**訪問 **/secure**這個路徑，但必須把認證帶上。帶上認證的方式，是在GET參數中，加上一個**Authorization**。我們輸入key值authorization,value值是“**bearer 我們的Token**”，然後送出，會得到**200 OK**。   
![7](images/4_get_test_and_ok.png)

- 接下來，我們故意弄亂Token 再重新發送。會得到 **401 unauthorized 錯誤**(未被授權).由此可知，若沒通過認證取得授權，是無法訪問加鎖的頁面的。
![8](images/5_use_wrong_token.png)

![9](images/6_get_401_error.png)
