# SQLite
Thư viện SQLite.
Thường chỉ sử dụng 2 file sqlite3.c và sqlite3.h

# Lệnh thường dùng
#### Mở
`sqlite3_open(const char *filename, sqlite3 **ppDb)`
>Chương trình con này mở một kết nối tới một SQLite database file và trả về một đối tượng database connection để được sử dụng bởi các chương trình con SQLite khác
>Nếu tham số filename là NULL hoặc ':memory:', sqlite3_open() sẽ tạo một in-memory database trong RAM mà chỉ tồn tại trong suốt phiên đó.
>Nếu filename không là NULL, sqlite3_open() cố gắng mở một database file bởi sử dụng giá trị của nó. Nếu không có file nào tồn tại với tên đó, hàm sqlite3_open() sẽ >mở một database file mới bởi tên đó
