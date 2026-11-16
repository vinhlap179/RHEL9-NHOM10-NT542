Mô hình hoạt động
Controller: Máy Windows chạy WSL2 (Ubuntu) để cài Ansible. (Hoặc chạy 3 máy ảo)
Workers: 2 máy ảo RHEL 9 (chạy VirtualBox/VMware) có bật SSH.
Ansible trên WSL2 sẽ SSH vào 2 máy RHEL 9 này để cấu hình tự động.

Quy trình làm việc với GitHub:
Bước 1: Mọi người git clone repo RHEL9-NHOM10-NT542 về máy.
Bước 2: Vào thư mục ansible, copy file inventory.ini.example thành inventory.ini. Tự sửa lại IP trong file này cho đúng với 2 máy ảo RHEL 9 của máy mình (Lưu ý: File inventory.ini sẽ KHÔNG được push lên GitHub để tránh ghi đè IP của nhau).
Bước 3: viết code Ansible (.yml) hoặc script (.sh).
Bước 4: Chạy test trên máy mình bằng lệnh: ansible-playbook -i inventory.ini playbook.yml. Nếu thấy báo failed=0 là thành công.
Bước 5: Chụp ảnh màn hình Terminal (để làm báo cáo) -> git add . -> git commit -m "..." -> git push.

Lưu ý:
Tuyệt đối KHÔNG push file inventory.ini hay mật khẩu/SSH key lên GitHub.
Code xong nhớ lưu file. Ai làm Chương nào thì tạo code trong thư mục Phase đó.

