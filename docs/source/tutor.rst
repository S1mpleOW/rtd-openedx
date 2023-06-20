Cài đặt Tutor
=============

Yêu cầu trước khi cài đặt
-------------------------
 * Hệ điều hành được hỗ trợ: Tutor chạy tốt trên các hệ điều hành dựa trên UNIX 64-Bit. Tutor cũng có thể hoạt động tốt trên Windows (với `WSL 2 <https://learn.microsoft.com/en-us/windows/wsl/install>`_).
 * Phần mềm bắt buộc:
   * `Docker <https://docs.docker.com/engine/install/>`_: v18.06.0+
   * `Docker Compose <https://docs.docker.com/compose/install/>`_: v1.22.0+
 * Đảm bảo các dịch vụ web khác không chạy trên các cổng 80 và 443.
 * Phần cứng:
   *	Cấu hình tối thiểu: RAM 4 GB, 2 CPU, dung lượng đĩa 8 GB.
   *	Cấu hình đề xuất: RAM 8 GB, 4 CPU, dung lượng đĩa 25 GB.
                                                                                                                                       
Tiến hành cài đặt
-----------------

.. code-block:: python

    pip install "tutor[full]"

Chạy Open edX
-------------
Sau khi cài đặt thành công, chạy Open edX bằng câu lệnh: 

.. code-block:: python

    tutor local launch

Ngay sau khi chạy câu lệnh trên, chúng ta sẽ được yêu cầu trả lời một số câu hỏi về các thông tin cấu hình cho hệ thống Open edX của mình.

Tiếp đó hệ thống sẽ khởi tạo các file cấu hình. Bắt đầu quá trình tải xuống các Docker image.

Kết quả của quá trình trên là một hệ thống Open edX hoàn chỉnh, sẵn sàng cho việc đẩy lên môi trường production (hiện tại mới nhất là phiên bản `Olive <https://edx.readthedocs.io/projects/edx-installing-configuring-and-running/en/latest/platform_releases/olive.html>`_).

Toàn bộ quá trình trên  có thể mất tới 10 phút trên một máy chủ có băng thông tốt. Lưu ý rằng môi trường host sẽ không bị ảnh hưởng theo bất kỳ cách nào, vì mọi thứ đều chạy bên trong Docker container. 

Tạo mới tài khoản người dùng với quyền truy cập nhân viên và quản trị viên
--------------------------------------------------------------------------
Sau khi chạy thành công server Open edX, chúng ta cần phải tạo mới tài khoản người dùng bằng câu lệnh:

.. code-block:: python

    tutor local do createuser --staff --superuser yourusername user@email.com

Ngay sau khi chạy câu lệnh trên, người dùng sẽ được hệ thống yêu cầu cài đặt mật khẩu tương ứng cho tài khoản.

Thêm khóa học trải nghiệm vào hệ thống 
--------------------------------------
Nếu đây là lần đầu chúng ta cài đặt server Open edX, hệ thống lúc này sẽ chưa có bất kỳ một khóa học nào. Để thêm mới một khóa học trải nghiệm mà Open edX đã cung cấp sẵn, chạy câu lệnh:

.. code-block:: python

    tutor local do importdemocourse

Cấu hình theme cho hệ thống
---------------------------
Theme mặc định của Open edX khá là “nhạt nhẽo”, vì vậy chúng ta có thể thay đổi theme bằng câu lệnh sau:

.. code-block:: python

    tutor local do settheme mytheme

Ngoài ra, Open edX cũng phát triển `Indigo <https://github.com/overhangio/tutor-indigo>`_, một mã nguồn mở có thể tùy chỉnh theme với Tutor.



   

                                                                                                                                
                                                                                                                                      