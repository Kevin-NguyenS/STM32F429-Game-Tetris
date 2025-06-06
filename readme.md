# 🎮 Tetris Game on STM32F429I-DISC1 using TouchGFX(working)

## 📌 Mục tiêu

Phát triển trò chơi **Tetris cổ điển** trên kit **STM32F429I-DISC1**, sử dụng giao diện đồ họa TouchGFX và điều khiển bằng **4 nút bấm cứng**.  
Trò chơi bao gồm:
- Hiển thị khối Tetris theo thời gian thực.
- Điều khiển bằng 4 nút: trái, phải, xoay, rơi nhanh.
- Lưu và hiển thị điểm số.
- Phát âm thanh khi ghi điểm (nâng cao).
- Sử dụng **RNG phần cứng** của STM32F4 để sinh khối ngẫu nhiên.
- (Tuỳ chọn) Lưu highscore trong bộ nhớ flash hoặc backup SRAM.

## 🧰 Yêu cầu phần cứng

- STM32F429I-DISC1 (có tích hợp LCD 2.4”)
- 4 nút bấm ngoài gắn vào GPIO
- Loa hoặc buzzer (nối DAC hoặc PWM)
- Dây jumper để kết nối GPIO
- Nguồn 5V hoặc kết nối qua USB


## 🧩 Tính năng

### ✅ Đã hoàn thành:
- Hiển thị lưới và các khối Tetris trên màn hình LCD
- Điều khiển bằng 4 nút GPIO: trái, phải, xoay, rơi nhanh
### 🚧 Đang phát triển:
- Logic kiểm tra va chạm, di chuyển, sinh khối ngẫu nhiên
- Tính điểm khi xoá hàng
- Lưu high score vào Flash hoặc Backup SRAM
- Âm thanh khi xoá hàng
- Tăng tốc độ theo thời gian

## 🎮 Điều khiển

| Nút bấm | GPIO | Chức năng |
|---------|------|-----------|
| Left    | PB0  | Di chuyển khối sang trái |
| Right   | PB1  | Di chuyển khối sang phải |
| Down    | PB2  | Làm khối rơi nhanh hơn |
| Rotate  | PB3  | Xoay khối theo chiều kim đồng hồ |

## 📈 Tính điểm

| Sự kiện | Điểm |
|---------|------|
| Xóa 1 hàng | +100 |

## 🔊 Âm thanh 

## 🔐 Lưu điểm cao (high score)

## 🖼️ Giao diện
- Lưới game: 10x20 ô khối, mỗi ô 16x16 px
- Giao diện tối giản, dễ nhìn, cập nhật mỗi frame

## 💡 Kỹ thuật hiển thị

- `getGrid()` trả về mảng 2 chiều `grid[20][10]`
- Trong `updateGrid()`, lặp qua từng hàng/cột:
  - Nếu giá trị != 0 → hiển thị Box/Image
  - Nếu bằng 0 → ẩn
- Dùng `block[row][col].setColor()để thay đổi hiển thị theo loại khối

## 📜 Giấy phép

Dự án này dành cho mục đích học tập, nghiên cứu vi điều khiển và giao diện đồ họa nhúng.  
Có thể sử dụng, sửa đổi tự do với mục đích cá nhân hoặc giáo dục.



