# Technical packet LED — {dự án}

Chỉ dùng cho LED/mapping/sân khấu. Tách dữ kiện vendor xác nhận và giả định preview. Phiếu trống không phải hồ sơ đã đủ để xuất cuối.

## Nhận diện phiên bản

- Packet version / ngày:
- Vendor / người xác nhận / bản drawing gốc:
- Show / rehearsal / deadline / múi giờ:
- Người gọi cue / người vận hành playback:

## Hình học và bản đồ pixel

Đính kèm mặt bằng, mặt đứng và pixel map có tọa độ. Ghi đơn vị gốc tọa độ, hướng trục và hướng màn.

| Screen ID | W×H vật lý | Đơn vị | W×H pixel thực | X/Y trong canvas tín hiệu | Hướng/góc | Gap/mask/vùng che |
|---|---|---|---|---|---|---|

- Canvas sáng tác W×H:
- Canvas tín hiệu W×H / output routing:
- Vị trí nhìn chính / camera / eyepoint nếu anamorphic:
- Vùng người đứng, IMAG và thông tin cần bảo vệ:

## Chuỗi phát và file nhận

- Server/player/processor / phiên bản / cấu hình liên quan:
- FPS nguồn / timeline / output chính xác (ghi phân số khi cần):
- Progressive/interlaced / timecode / DF-NDF nếu dùng:
- Container / codec / kích thước tối đa / giới hạn playback:
- Color space / transfer / range / bit depth / người áp transform:
- Alpha: không/có; straight/premultiplied:
- Audio sample rate / channel map / spec loudness nếu có:
- Trigger / đồng bộ / timecode / cách hold-loop-out:
- File mẫu được vendor chấp nhận và kết quả thử:
- Test grid/ID screen, màu, alpha, loop và tổng tải:

## Trạng thái và nghiệm thu

| Hạng mục | Đã xác nhận / giả định / còn thiếu | Nguồn/người xác nhận | Thời điểm cần | Kết quả test |
|---|---|---|---|---|

- Danh sách file show đúng phiên bản:
- Cue sheet / fallback / standby:
- Hệ thống đã test / ngày / người xác nhận:
- Những phần chưa test hoặc chưa được chốt:
- Thay đổi sau rehearsal và cue cần kiểm lại:
