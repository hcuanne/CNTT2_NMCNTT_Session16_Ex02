


# Phần 1. Phân tích

| Cache | Cookies |
|---|---|
| MB/GB | Khoảng 4KB |
| Lưu ảnh, CSS, JS | Lưu phiên đăng nhập |
| Tăng tốc tải trang | Duy trì đăng nhập |

Giải pháp: Dùng Persistent Cookies để ghi nhớ
đăng nhập và lưu giỏ hàng trên Server.

# Phần 2. Triển khai

Cookie mẫu:

`Set-Cookie: session_token=abc123; Max-Age=604800; HttpOnly; Secure; SameSite=Lax; Path=/`

- Max-Age: Duy trì 7 ngày.
- HttpOnly: Chặn JavaScript đọc Cookie.
- Secure: Chỉ gửi qua HTTPS.
- SameSite: Giảm nguy cơ CSRF.

# Phần 3. Kiểm thử trên macOS

1. Nhấn `Cmd + Option + I` mở DevTools.
2. Vào Application → Cookies.
3. Kiểm tra HttpOnly, Secure, Expires.
4. Hard Reload: `Cmd + Shift + R`.
5. Xóa Cache: Giữ nút Reload → chọn
   Empty Cache and Hard Reload (khi DevTools mở).


