#demo
// kiểm tra danh sách commit của nhánh đang đứng
    git log -- online // xem log, mỗi commit trên 1 dòng
// thực hiện tách nhánh: nhánh được tách sẽ chứa toàn bộ commit của nhánh cha(chứa toàn bộ code)
// git checkout tên_nhánh(nếu nhánh đó đã được tạo)
// git checkout -b tên_nhánh (nếu nhánh đó chưa được tạo) -> chỉ tạo ở local

giả sử nhánh develop đang có chức năng -> muốn người khác thực hiện làm việc cùng trên nhánh này 
    git push web204 develop -> tạo 1 nhánh develop trên github trắng ý như develop ở local
    
    - develop -> tạo nhánh add_user
            <- (khi thực hiện xong chức năng, commit và push lên)
            Hoàn thiện code ở nhánh add_user ->git add . -> git commit - "ND" -> git push
            Sau khi hoàn thiện -> gộp code vào nhánh làm việc gốc (develop): tạo pull request
                So sánh nhánh mới với nhánh gốc (develop <- add_user) thấy ko có vấn đề gì -> Merge

-Luôn để nhánh làm việc chính(develop) được update mới nhất so với develop trên github
    Quay về nhánh develop ở local(git checkout develop) không được làm việc trực tiếp ở trên nhánh này
    git pull web204 develop
------------- tên nhánh đang đứng: công việc

-master: tách nhánh làm việc chính develop (git checkout -b develop)
-develop: tách nhánh add_user (git checkout -b add_user)
-add_user: thực hiện code chức năng(tạo file add_user.php và thay đổi nội dung)
- add_user: commit -> push lên nhánh add_user trên github ( git add . -> git commit - m "Add user")-> git push web204 add_user)
github: Tạo pull request so sánh develop <- add_user, merge code nhánh add_user trên github vào nhánh develop trên github(Bấm vào nút Compare & pull request -> Create -> Merge)
-add_user: quay về nhánh develop(git checkout develop)
-develop: pull code mới nhất trên nhánh develop của github về nhánh develop local(git pull web204 develop)
            