Bước 1 : mkdir smart-farm/bin, smart-farm/config, smart-farm/data

Bước 2 : 

New-Item smart-farm\\config\\.env -force

(gi smart-farm\\config\\.env -Force).Attributes='Hidden' 

ls smart-farm\\config -Force 

Get -ChildItem thông thường không nhìn thấy file .env vì .env được gán là file ẩn nên get-childItem chỉ tìm thấy những thư mục bình thường không tìm file ẩn nên phải dung -force để get-childItem nhìn thấy file ẩn



Bước 3 : cp C:\\Users\\Public\\template.ps1 \~\\smart-farm\\bin\\pump\_control.ps1



Bước 4 : ls smart-farm -Recurse -Force 



\- Nếu gặp lỗi "Access to the path is denied"

gõ lệnh powershell:  Start-Process powershell -Verb RunAs





Nhật ký (Log) các câu lệnh PowerShell đã thực hiện:



|mkdir smart-farm/bin, smart-farm/config, smart-farm/data|tạo thư mục gồm 3 thư mục con bin,config và data|
|-|-|
|New-Item smart-farm\\config\\.env -force<br />(gi smart-farm\\config\\.env -Force).Attributes='Hidden'|tạo file ẩn <br />và xác nhận file|
|cp C:\\Users\\Public\\template.ps1 \~\\smart-farm\\bin\\pump\_control.ps1|sao chép và đổi tên file|
|ls smart-farm-Recurse -Force |xem danh sách các thư mục trong smart-farm|





Bản phân tích luồng IPO cho toàn bộ quá trình thiết lập căn cứ số này





|Input|Tạo thư mục (mkdir smart-farm/bin, smart-farm/config, smart-farm/data)<br />Tạo file ẩn (New-Item smart-farm\\config\\.env -force<br />(gi smart-farm\\config\\.env -Force).Attributes='Hidden')|
|-|-|
|Process|(1) mkdir tạo cây thư mục, (2) New-Item tạo .env + gi để chọn file chỉnh sửa + Attributes  ẩn file, (3) cp sao chép và đổi tên, (4) ls -Recurse -Force kiểm tra |
|Output|Cấu trúc smart-farm/ gồm bin/pump\_control.ps1, config/.env (ẩn), data/ (rỗng)|



