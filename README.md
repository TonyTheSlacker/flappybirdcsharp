# Flappy Bird (Windows Forms, .NET Framework 4.8)

## Giới thiệu
Bản mô phỏng Flappy Bird với ống xanh/đỏ, cơ chế bay mượt, điểm số dạng sprite.
Khi bắt đầu game mới sẽ có hộp chọn màu chim (Vàng/Xanh/Đỏ) bằng hình PNG trực quan.

## Yêu cầu
* Windows + .NET Framework 4.8
* Visual Studio 2019/2022 (khuyến nghị)

## Cách chạy nhanh
1.  Mở solution.
2.  Chọn cấu hình Release > Build.
3.  Chạy file: `flappy bird tesst\bin\Release\flappy bird tesst.exe`.

## Điều khiển
* **Space:** Vỗ cánh
* **Esc:** Tạm dừng / Tiếp tục
* **R:** Chơi lại
* **1/2/3:** Chọn màu chim ở màn hình chọn chim

## Tính năng chính
* Chọn màu chim bằng overlay PNG khi bắt đầu game.
* Ống xanh (dễ) và ống đỏ (khó), điểm tương ứng 1/2.
* Khoảng trống giữa ống thay đổi mạnh theo từng cột (ít lặp).
* Âm thanh đồng bộ: điểm, va chạm, rơi.
* Điểm số hiển thị bằng sprite số.

## Thư mục / Files đáng chú ý
* `Form1.cs`: Logic game, vật lý, va chạm, âm thanh, chọn chim.
* `Form1.Designer.cs`: Khai báo control.
* `Properties\Resources.respx`: Sprites/âm thanh.
