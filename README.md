# SQLite
Thư viện SQLite.
Thường chỉ sử dụng 2 file sqlite3.c và sqlite3.h

# Lệnh thường dùng
#### Mở
`sqlite3_open(const char *filename, sqlite3 **ppDb)`
>Chương trình con này mở một kết nối tới một SQLite database file và trả về một đối tượng database connection để được sử dụng bởi các chương trình con SQLite khác.
>Nếu tham số filename là NULL hoặc ':memory:', sqlite3_open() sẽ tạo một in-memory database trong RAM mà chỉ tồn tại trong suốt phiên đó.
>Nếu filename không là NULL, sqlite3_open() cố gắng mở một database file bởi sử dụng giá trị của nó. Nếu không có file nào tồn tại với tên đó, hàm sqlite3_open() sẽ >mở một database file mới bởi tên đó.

#### Thực thi
`sqlite3_exec(sqlite3*, const char *sql, sqlite_callback, void *data, char **errmsg)`
>Chương trình con này cung cấp một cách thức nhanh và dễ dàng để thực thi các lệnh SQL được cung cấp bởi tham số sql mà có thể bao gồm nhiều hơn một lệnh SQL
>Ở đây, tham số đầu tiên sqlite3 là đối tượng open database, sqlite_callback là một callback từ đó data là tham số đầu tiên và errmsg sẽ được trả về để bắt bất kỳ >lỗi nào được tạo ra bởi chương trình con đó
>Chương trình con sqlite3_exec() phân tích và thực thi mỗi lệnh đã cho trong tham số sql tới khi nó tiến tới phần cuối của chuỗi hoặc bắt gặp một lỗi

#### Đóng
`sqlite3_close(sqlite3*)`
>Chương trình con này đóng một database connection đã được mở trước đó bởi lời gọi tới hàm sqlite3_open(). Tất cả các lệnh đã chuẩn bị mà được gắn kết với >connection nên bị kết thúc trước khi đóng connection đó.
>Nếu còn tồn tại bất kỳ truy vấn nào chưa được kết thúc, sqlite3_close() sẽ trả về SQLITE_BUSY với một thông báo lỗi là Unable to close due to unfinalized statements
