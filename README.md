# FrequentPatternMining
## Dữ liệu
`orders.csv` và `products.csv` biểu diễn dữ liệu mua hàng được lấy mẫu từ hơn ba triệu đơn hàng tạp hóa của 200,000 người dùng Instacart users
- `orders.csv` chứa các giao dịch đã thực hiện. Mỗi giao dịch được thể hiện bằng một hay nhiều dòng, thông tin trên mỗi dòng bao gồm: mã giao dịch (`order_id`), mã sản phẩm (`product_id`), thứ tự bỏ vào giỏ (`add_to_cart_order`), và sản phẩm này có được mua lại hay không (`reordered`). Ta chỉ quan tâm hai trường đầu tiên
- `products.csv` chứa các sản phẩm bày bán trong cửa hàng. Mỗi dòng trình bày thông tin của một sản phẩm, bao gồm: mã sản phẩm (`product_id`), tên sản phẩm (`product_name`), và thông tin khác (`aisle_id` và `department_id`). Ta chỉ quan tâm hai trường đầu tiên.

## Xử lý & kết luận
Áp dụng giải thuật FP-Tree cho khai thác mẫu phổ biến và luật kết hợp trong gói pyspark.ml.fpm lên dữ liệu được cho ở trên. Thử nghiệm với 4 ngưỡng support và confidence khác nhau. Cải thiện được nhược điểm của giải thuật, đó là mệnh đề hệ quả từ chỉ có duy nhất 1 giá trị thành có nhiều giá trị khả thi hơn, từ đó tăng số luật khả thi

Qua phân tích và cải thiện giải thuật, kết luận được luật sau: 
> Nếu khách hàng mua **[Organic Hass Avocado, Organic Strawberries]** thì xác suất mua **Bag of Organic Bananas** là 46.13%. Ngoài ra, số giao dịch mà khách hàng mua cả 3 món chiếm 0.5% trên tổng số giao dịch
