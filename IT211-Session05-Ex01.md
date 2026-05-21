IT211-Session05-Ex01
1. REST yêu cầu dùng danh từ (số nhiều) cho đường dẫn (URL), không dùng động từ là ĐÚNG
	- Ví dụ đúng: GET /products
	- Ví dụ sai: GET /getProducts

	- Ví dụ cho API quản lý sinh viên:
		+ Ví dụ đúng:
			- GET /students
			- POST /students
		+ Ví dụ sai:
			- GET /getStudents
			- POST /createStudent

2. Các phương thức HTTP
	- Method GET:
		+ Mục đích chính: Lấy dữ liệu
		+ Có body không: Thường không có body
	- Method POST:
		+ Mục đích chính: Tạo mới dữ liệu
		+ Có body không: Có
	- Method PUT:
		+ Mục đích chính: Cập nhật toàn bộ dữ liệu
		+ Có body không: Có
	- Method PATCH:
		+ Mục đích chính: Cập nhật một phần dữ liệu
		+ Có body không: Có
	- Method DELETE:
		+ Mục đích chính: Xóa dữ liệu
		+ Có body không: Thường không có

3. Phân biệt PUT và PATCH
	- Giả sử có một sản phẩm: { "id": 1, "name": "Bút bi", "price": 5000 }
		+ Nếu dùng PUT /products/1 với body { "name": "Bút mực" } thì sản phẩm sau khi cập nhật sẽ có id giữ nguyên, name sẽ đổi sang "Bút mực" và 
price sẽ mang giá trị null
		+ Nếu dùng PATCH /products/1 với body { "name": "Bút mực" } thì sản phẩm sau khi cập nhật sẽ có id và price vẫn sẽ giữ nguyên còn name thì sẽ
đổi từ "Bút bi" sang "Bút mực"
	- Giải thích sự khác biệt:
		+ PUT sẽ cập nhật lại toàn bộ object
		+ PATCH sẽ cập nhật một phần được chỉ định của object đó

4. Mã trạng thái HTTP (status code)
	- Mã 200:
		+ Ý nghĩa: OK
		+ Tình huống ví dụ: Lấy danh sách bất kỳ thành công
	- Mã 201:
		+ Ý nghĩa: Create
		+ Tình huống ví dụ: Tạo thành công một đối tượng

	- Mã 204:
		+ Ý nghĩa: No Content
		+ Tình huống ví dụ: Xóa dữ liệu thành công và không trả về body

	- Mã 400:
		+ Ý nghĩa: Bad Request
		+ Tình huống ví dụ: Client gửi sai dữ liệu

	- Mã 404:
		+ Ý nghĩa: Not Found
		+ Tình huống ví dụ: Không tìm thấy dữ liệu
	- Mã 500:
		+ Ý nghĩa: Internal Server Error
		+ Tình huống ví dụ: Lỗi phía server