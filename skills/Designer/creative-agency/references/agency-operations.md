# Vận hành một dự án sáng tạo

Đọc khi có nhiều deliverable, người tham gia, nhà cung cấp, deadline hoặc vòng sửa. Tổ chức công việc để tạo sản phẩm đúng, không tạo hồ sơ quản trị cho có.

## 1. Nhận brief và định nghĩa phạm vi

Khôi phục dữ kiện từ hội thoại, file, brand guide và nội dung đã chốt. Với dự án lớn, dùng [mẫu brief](../assets/creative-brief.md); với asset nhỏ, vài dòng là đủ.

Phân biệt bốn lớp thường bị trộn:

| Lớp | Câu hỏi quyết định | Ví dụ |
|---|---|---|
| Kết quả kinh doanh/tổ chức | Việc này giúp điều gì? | Tăng đăng ký đủ điều kiện |
| Kết quả truyền thông | Người xem cần hiểu/cảm/đổi hành vi gì? | Hiểu lợi ích và tin đủ để đăng ký |
| Nhiệm vụ sáng tạo | Tạo trải nghiệm nào để tác động? | Một lời mời có bằng chứng, dễ nhận diện |
| Sản phẩm bàn giao | File nào phải dùng được ở đâu? | KV, landing hero, clip, backdrop |

Đừng xem danh sách kích thước là creative brief. Ngược lại, một câu “sang trọng, wow” chưa phải thông số sản xuất. Tách yêu cầu bất biến (copy, logo, dữ kiện, khổ đã xác nhận) khỏi phần được sáng tạo.

Thiếu dữ kiện: nêu giả định để tiếp tục concept, nhưng đánh dấu các điểm không thể đoán cho final (ngày/địa điểm, claim, pixel map, dieline, bản quyền tài sản được dùng). Đặt một cụm câu hỏi ngắn vào thời điểm cần trả lời. Không bắt người dùng tự điền toàn bộ biểu mẫu trước khi bắt đầu.

## 2. Trách nhiệm và checkpoint

Một người/agent có thể kiêm nhiều vai; không giả vờ đã có đội ngũ thật.

| Vai trò | Chịu trách nhiệm | Artifact quyết định |
|---|---|---|
| Strategy/planning | Mục tiêu, audience, insight, message, đo lường | Creative brief, message hierarchy |
| Creative direction | Ý tưởng xuyên hệ thống và chọn hướng | Concept rationale, mood/style board |
| Art/copy direction | Bố cục, type, hình ảnh, wording | Master layout/styleframe/copy deck |
| Producer | Phạm vi, phụ thuộc, khả năng làm, thời gian | Asset matrix, tiến độ, technical packet |
| Craft specialists | 2D, 3D, motion, edit, sound | Source và bản xuất đúng hạng mục |
| QC/integration | Nội dung, nhất quán, trải nghiệm và spec | Bản đã kiểm, lỗi còn lại, manifest |

Khi chia việc, giao chung một brief có phiên bản, định hướng đã chọn, copy/asset bất biến, đầu ra, file sở hữu và điều kiện hoàn thành. Giao các nhánh độc lập; tránh nhiều người đồng thời sửa cùng master. Người tích hợp kiểm chéo các nhánh trước bàn giao. Nếu không có subagent, tự thực hiện các góc nhìn này mà không mô tả đó là phản biện độc lập.

Checkpoint là kiểm soát nội bộ. Chỉ trình quyết định cần người dùng chọn khi họ muốn duyệt, khi còn mâu thuẫn thực sự hoặc thay đổi tạo cam kết lớn ngoài quyền đã có. Đã được giao triển khai thì tiếp tục đến đầu ra.

## 3. Lập kế hoạch theo phụ thuộc

Đi từ ngày sử dụng thực tế trở về: bàn giao cho vendor → thử trên thiết bị/proof → export/render → conform/finishing → master → concept/brief. Dùng múi giờ người dùng, không suy ra từ máy thực thi.

Xác định đường găng bằng phụ thuộc thật: final copy ảnh hưởng type; camera lock ảnh hưởng render; pixel map ảnh hưởng bố cục LED; duyệt model ảnh hưởng animation; âm nhạc/VO ảnh hưởng nhịp. Chạy song song research, chuẩn bị asset và tổ chức source khi không bị phụ thuộc.

Ước lượng theo các phần: nghiên cứu/concept, sản xuất, render/export, QC, sửa và thời gian bên ngoài. Nêu phạm vi ước lượng và giả định; không hứa giờ render nếu chưa benchmark. Dùng một đoạn test trên máy thực tế khi thời gian render là rủi ro. Chừa khả năng xử lý lỗi export/thiết bị, không coi mọi thời gian trống là có thể thêm scope.

Nếu deadline không đủ, đề xuất tradeoff cụ thể: giảm số cảnh 3D thay vì giảm toàn bộ QC; một master có adaptation tốt thay vì nhiều concept chưa hoàn thiện; dùng kiểu chuyển động nhẹ hơn thay vì hạ độ đọc chữ. Không tự bỏ deliverable đã cam kết mà không nêu ảnh hưởng.

## 4. Asset matrix và quản lý phiên bản

Dùng [deliverables.csv](../assets/deliverables.csv) khi có nhiều đầu ra. Mỗi dòng xác định ai dùng, mục đích, phiên bản ngôn ngữ/copy, tỷ lệ/kích thước, thời lượng, thông số nhận file, nguồn master, trạng thái, bước kiểm đã thực hiện. Spec chưa có ghi “chờ xác nhận”, không điền số để làm bảng trông hoàn chỉnh.

Tổ chức thư mục vừa đủ, ví dụ:

```text
brief/       dữ kiện và quyết định
source/      file chỉnh sửa, liên kết và tài sản hợp lệ
work/        bản thử và render tạm
review/      preview có phiên bản
delivery/    đúng tập file bàn giao
```

Tên file nên biểu đạt dự án/hạng mục/format/ngôn ngữ/version/trạng thái; ví dụ `event_kv_vertical_vi_v03_review.png`. Dùng mã ASCII dễ tương thích nếu vendor yêu cầu; nội dung trong file vẫn giữ tiếng Việt. Không dùng chuỗi `final_final2`. Không ghi đè bản đã được dùng ngoài dự án mà không giữ một bản có thể truy hồi.

Trạng thái hữu ích: draft → review → revision → ready-for-delivery → delivered. **User-approved** chỉ khi có bằng chứng người dùng chấp thuận bản cụ thể; **device-tested** chỉ khi có test thực tế. Tự đạt QC không đồng nghĩa hai trạng thái này.

Với event/campaign, kiểm thêm độ bao phủ các nhiệm vụ theo [Campaign coverage](campaign-coverage.md). Gắn derivative với thiết kế gốc; không cộng mockup, source và resize như những ý tưởng mới. Khi mẫu đạt, tiếp tục toàn bộ phạm vi đã giao. Nghiên cứu và look development có thể lặp trong sản xuất; lịch phụ thuộc không được ép mọi khám phá chấm dứt ngay sau moodboard.

## 5. Feedback và thay đổi scope

Chuyển feedback thành vấn đề quan sát được, không tranh luận để bảo vệ ý tưởng. “Chưa wow” có thể do concept quá quen, tỷ lệ nhút nhát, hình giả, craft chữ yếu hoặc nhầm ngữ cảnh; xem bản thật và tìm nguyên nhân trước khi thêm hiệu ứng.

Phân biệt:

- Sửa lỗi: chữ sai, logo sai, méo hình, thiếu hạng mục, spec sai — sửa ngay trong phạm vi.
- Tinh chỉnh: hierarchy, kerning, timing, màu/ánh sáng — giữ concept và phần đã chốt.
- Đổi hướng: audience/message/concept/format mới — cập nhật brief và phụ thuộc liên quan.

Nếu feedback mâu thuẫn, ưu tiên chỉ dẫn mới nhất và đúng phạm vi; hỏi một câu quyết định nếu không thể dung hòa. Ghi quyết định quan trọng bằng phiên bản, lý do và ảnh hưởng; không lập biên bản dài cho mỗi thay đổi nhỏ. “Chốt option 1” không có nghĩa mọi bản sửa sau đều được duyệt.

## 6. Hợp tác bên ngoài và nghiệm thu

Chuẩn bị gói vendor cụ thể: artwork đúng tỷ lệ, spec đã biết, câu hỏi chưa chốt, preview và yêu cầu proof/playback. Viết sẵn email/brief khi hữu ích; chỉ gửi khi có chỉ dẫn cho phép gửi. Dự toán tách công thiết kế, sản xuất, media, tài sản/license, thuê thiết bị và contingency khi được yêu cầu; không bịa báo giá thị trường hoặc nhà cung cấp.

Tại nghiệm thu, đối chiếu danh sách hạng mục và file thực. Các vấn đề như gia công, rigging, tải trọng, điện và yêu cầu venue do đơn vị có chuyên môn xác nhận; mockup không phải hồ sơ kỹ thuật. Với print/LED, giao kèm trạng thái test để người tiếp nhận không nhầm preview là bản đã chứng minh trên thiết bị.

Sau dự án, nếu có dữ liệu/phản hồi: điều gì hoạt động, điều gì thất bại, nguyên nhân nào đã chứng minh, lần sau đổi gì. Tách ý kiến cá nhân, kết quả đo lường và suy luận của agent. Không tuyên bố tự học liên tục hoặc theo dõi bên ngoài phiên làm việc.
