# Cài đặt Gitlab
## Chuẩn bị
1 máy ubuntu để làm gitlab-server


## Thực hiện
### Bước 1: Cài đặt gitlab-ee package

Tải gitlab-ê package [tại đây](https://packages.gitlab.com/gitlab/gitlab-ee)

Ở đây, ta chọn phiên bản sau:

![alt text](../images/gitlab_01.png)

```bash
curl -s https://packages.gitlab.com/install/repositories/gitlab/gitlab-ee/script.deb.sh | sudo bash
```

```bash
sudo apt-get install gitlab-ee=18.7.1-ee.0
```

### Bước 2: add host cho gitlab

```bash
vi /etc/hosts
```

![alt text](../images/gitlab_02.png)

### Bước 3: Sửa URL của gitlab

Mở file cấu hình gitlab

```bash
vi /etc/gitlab/gitlab.rb
```

![alt text](../images/gitlab_03.png)

Sửa thành tên mà bạn điều chỉnh trong `/etc/hosts` ở đây là: `git.server.tech`

Sau đó chạy câu lệnh sau để áp dụng

```bash
gitlab-ctl reconfigure
```

### Bước 3: add host trên window

![alt text](../images/gitlab_04.png)

### Bước 4: Truy cập trên browser

![alt text](../images/gitlab_05.png)

tài khoản mặc định sẽ là `root`

mật khẩu sẽ nằm trong `/etc/gitlab/initial_root_password`

![alt text](../images/gitlab_06.png)

Ta copy và đăng nhập trên browser:

![alt text](../images/gitlab_07.png)

### Bước 5: Tắt tính năng tạo mởi User

Khi cần tạo 1 tk root thì chính chúng ta sẽ tạo chứ không phải user tạo

![alt text](../images/gitlab_08.png)

Sau đó nhấp vào `save change`

### Bước 6: Tắt Default auto devops

![alt text](../images/gitlab_09.png)

### Bước 6: Đổi mk user root

![alt text](../images/gitlab_10.png)

### Bước 7: Site Admin

Ở đây, ta có thể tạo 1 user mới:

![alt text](../images/gitlab_11.png)

Nhập thông tin:

![alt text](../images/gitlab_12.png)

Muốn set quyền cho user này ta chọn ở phần `User type`:

![alt text](../images/gitlab_13.png)

Nhấp vào `create user` sau đó chọn `edit` để tạo mk cho user này:

![alt text](../images/gitlab_14.png)

