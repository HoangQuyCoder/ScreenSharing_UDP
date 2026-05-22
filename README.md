# 📺 ScreenSharing_UDP

Ứng dụng **chia sẻ màn hình thời gian thực** sử dụng giao thức **UDP** được viết bằng **C# .NET Windows Forms**.

## 📋 Giới thiệu

Dự án cho phép **nhiều Client** kết nối đến **Server** để chia sẻ màn hình của họ. Server sẽ nhận và hiển thị đồng thời nhiều màn hình từ các client khác nhau.

Đây là ứng dụng học tập và demo về **lập trình mạng UDP**, **xử lý hình ảnh**, **nén dữ liệu (GZip)** và **chia màn hình thời gian thực**.

## ✨ Tính năng chính

- **Giao thức UDP**: Tốc độ cao, phù hợp cho streaming
- **Hỗ trợ nhiều Client**: Server có thể xem nhiều màn hình cùng lúc
- **Nén dữ liệu**: Sử dụng **GZip** + **JPEG** để giảm băng thông
- **Chia màn hình theo chunk**: Phân mảnh hình ảnh để truyền ổn định
- **Kết nối bằng IP + Port**
- **Điều khiển Start/Stop** chia sẻ màn hình
- **Hiển thị danh sách client** đang kết nối
- **Xử lý ngắt kết nối** và dừng chia sẻ

## 🛠 Công nghệ sử dụng

- **Ngôn ngữ**: C# (.NET Framework / Windows Forms)
- **Giao thức**: UDP (UdpClient)
- **Nén dữ liệu**: GZipStream
- **Hình ảnh**: Bitmap, JPEG compression
- **Đa luồng**: Thread + Task

## 📁 Cấu trúc dự án
```bash
ScreenSharing_UDP/
├── ShareScreen.sln
├── Server/
│   ├── Server.cs              # Form server chính
│   ├── Program.cs
│   └── Server.csproj
├── Client/
│   ├── Client.cs              # Form client chính
│   ├── Program.cs
│   └── Client.csproj
└── README.md
```
text## 🚀 Hướng dẫn sử dụng

### 1. Chạy Server

1. Mở solution `ShareScreen.sln`
2. Chạy project **Server**
3. Nhập **IP** (thường là `127.0.0.1` khi test local) và **Port** (ví dụ: `5000`)
4. Nhấn **Start Server**

### 2. Chạy Client

1. Chạy project **Client** (có thể chạy nhiều instance)
2. Nhập **IP** và **Port** của Server
3. Nhấn **Connect**
4. Nhấn **Start Sharing** để bắt đầu chia sẻ màn hình
5. Nhấn **Stop Sharing** để dừng

> **Lưu ý**: Khi test trên cùng máy, dùng IP `127.0.0.1`.  
> Khi test qua mạng LAN, dùng IP LAN của máy Server.

## ⚡ Đặc điểm kỹ thuật

- Màn hình được chụp ở độ phân giải **1920x1080**
- Chất lượng JPEG **75%**
- Kích thước chunk tối ưu cho UDP (~65KB)
- Tự động reconnect và xử lý lỗi cơ bản
- Hiển thị ảnh theo tỷ lệ (Zoom)

## 🔧 Cải tiến có thể làm sau

- Thêm mã hóa dữ liệu (AES)
- Hỗ trợ điều khiển từ xa (Remote Control)
- Tối ưu tốc độ FPS
- Giao diện đẹp hơn (Dark mode, fullscreen view)
- Hỗ trợ WebRTC hoặc TCP fallback
- Thêm ghi hình (Recording)

## 📌 Lưu ý

- UDP **không đảm bảo** thứ tự gói tin → có thể bị lag hoặc mất khung hình ở mạng kém
- Dự án phù hợp để học **Network Programming** và **Multimedia Streaming**
