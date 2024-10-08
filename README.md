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


![3](images/0_use_postman.png)

![5](images/3_response_header.png)

![7](images/4_get_test_and_ok.png)

![8](images/5_use_wrong_token.png)

![9](images/6_get_401_error.png)
