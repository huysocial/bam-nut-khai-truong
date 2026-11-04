# Bấm Nút Khai Trương – VNPT

Tool nội bộ giúp VNPT các tỉnh/thành tự dựng 2 video nghi thức nhấn nút khai trương (File 1 – Màn chờ, File 2 – Kích hoạt) để chiếu lên màn LED sự kiện.

- Chạy: mở trang GitHub Pages của kho này bằng Chrome hoặc Edge trên máy tính.
- Bản đang đăng: **v1.5** (30/10/2026).
- File gốc và hồ sơ (URD, MAP, CHANGELOG) do Ban Truyền thông quản lý ở thư mục `1. APP/vnpt-bam-nut-khai-truong` trên Google Drive. Không sửa `index.html` trực tiếp trên GitHub.

## Thư viện chung trên GitHub (chỉ Ban Truyền thông cập nhật)

Tool tự đọc `thu-vien.json` và các file trong thư mục `media/`. Người dùng ở tỉnh chỉ xem và chọn, không tải lên được.

Thêm 1 tài nguyên:
1. Tải file vào thư mục `media/` (mỗi file dưới 20 MB, tên không dấu, không khoảng trắng).
2. Thêm 1 dòng vào `thu-vien.json`, phân cách các dòng bằng dấu phẩy.

| kind | Dùng cho | opts |
|---|---|---|
| `effect` | Hiệu ứng File 2 (MP4 nền đen) | `"slot"`: `"press"` nhấn nút · `"count"` mỗi số (đúng 1 giây) · `"trans"` chuyển cảnh (≤ 1 giây, kết thúc chớp trắng, `"lead"`: số giây bắt đầu trước bùng nổ, mặc định 0.6). `"blend": "screen"` cho nền đen |
| `resultbg` | Nền khung kết quả (lặp) | — |
| `background` | Nền màn chờ (lặp) | — |
| `button` | Mẫu nút (PNG/SVG nền trong suốt) | — |
| `logo` | Logo chuẩn | — |
| `audio` | Âm thanh (lưu sẵn, phát ở đợt 2) | `"slot"`: `"loop"`, `"press"`, `"count"`, `"boom"` |

Ví dụ:

```json
{
  "items": [
    {"kind": "effect", "name": "Mạch điện xanh", "url": "media/so-mach-dien.mp4", "opts": {"slot": "count", "blend": "screen"}},
    {"kind": "effect", "name": "Xoáy lốc trắng", "url": "media/chuyen-canh-xoay.mp4", "opts": {"slot": "trans", "blend": "screen", "lead": 0.6}},
    {"kind": "resultbg", "name": "Thành phố pháo hoa", "url": "media/nen-ket-qua-thanh-pho.mp4"}
  ]
}
```

Lưu ý: kho Public, ai có link đều tải được các file trong `media/`. Chỉ đặt tài nguyên miễn phí đã kiểm giấy phép, không đặt nội dung nội bộ.
