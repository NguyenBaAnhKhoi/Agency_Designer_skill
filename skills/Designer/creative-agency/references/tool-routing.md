# Chọn công cụ theo đầu ra

Đọc khi chọn pipeline, cần file native/editable, hoặc công cụ không đủ. Các tên dưới đây là skill có trong môi trường tại lúc xây dựng; kiểm lại catalog hiện tại. Nếu thiếu, dùng tài liệu tự chứa của creative-agency và công cụ phù hợp đang có. Không bắt cài plugin chỉ vì một lựa chọn được nêu ở đây.

## Quyết định trước khi mở công cụ

Xác định đầu ra cần **ảnh phẳng, vector, layout có chữ sống, scene 3D, timeline, video render hay gói vendor**. Sau đó kiểm nguồn và khả năng export thực. Chọn công cụ vì loại file và mức chỉnh sửa, không vì nó dễ gọi nhất.

| Nhu cầu | Cách định tuyến khi có sẵn | Điều phải kiểm |
|---|---|---|
| Nghiên cứu và art direction sâu | `creative-design-director` | Giữ brief hiện tại; đọc feedback cũ đúng dự án, không áp thẩm mỹ khách cũ |
| Kể chuyện/dựng biên tập | `creative-video-editor` | Footage, nội dung, nguồn tiếng và nhu cầu timeline/render |
| Tạo/sửa ảnh raster | `imagegen` và công cụ tạo/sửa ảnh phù hợp; Kling nếu được chọn và có hỗ trợ | Ảnh tham chiếu, giới hạn chữ/logo, transparency, độ chính xác và output |
| Layout/component trong Figma | Các skill `figma-use`, `figma-create-new-file`, `figma-generate-design` liên quan | Thực hiện prerequisite của công cụ; nguồn chỉnh sửa được và export |
| Canva/Adobe | Skill ứng với chỉnh thiết kế, template, resize hoặc ứng dụng được chọn | Asset người dùng, phạm vi sửa, file nguồn và khả năng xuất thật |
| Motion từ thiết kế/code | Các skill Remotion hoặc công cụ motion hiện có | Preview và render thật; font/media, frame rate, tính chỉnh sửa |
| Video dựng/generative | `openmontage`, skill Kling video hoặc workflow editor phù hợp | Media, continuity, clip output, thời gian/chi phí và quyền đã có |
| Voice/music/SFX | Skill ElevenLabs tương ứng khi được dùng | Nội dung, giọng, cách phát âm, quyền sử dụng, chi phí và file audio thật |
| 3D scene/render | Blender/C4D/Unreal hoặc công cụ 3D thực sự truy cập được | Có ứng dụng/API/CLI, version, scene, tài sản, render và export |
| Slide/document/PDF/sheet | Skill chuyên dụng tương ứng | Layout/text, render/preview, font và kiểm export |
| Website chiến dịch | Skill Sites hoặc công cụ web được chọn | Brief tương tác, responsive, dữ liệu, accessibility và quyền publish |

Không áp quy trình của ứng dụng khác lên ứng dụng người dùng đã chọn. Đọc skill cần thiết theo quy định của công cụ; bảng này không thay manual hoặc mở rộng quyền sử dụng. Tool names, tham số và endpoint phải lấy từ công cụ/documentation hiện tại, không bịa API trong lúc chạy.

## Giữ workflow khi đi qua nhiều công cụ

Trước pipeline dài, thử một asset nhỏ qua đủ vòng: tạo → chuyển → chỉnh → export → mở ở nơi nhận. Với chữ/vector, kiểm font và scale; với 3D, units/camera/color/alpha; với video, timebase/color/audio. Chi phí phát hiện lỗi lúc này thấp hơn sau khi nhân bản hoặc render dài.

Giữ source ở định dạng công cụ tạo, và ghi phần nào chuyển sang phẳng. Chọn handoff có khả năng chỉnh đúng mục đích: layer/component có tên, text còn sống, media relink được, frame handles nếu cần. Không hứa round-trip đầy đủ giữa mọi ứng dụng.

Khi công cụ thiếu, chia công việc thành phần làm được và phần bị chặn. Ví dụ không có renderer 3D thì vẫn làm art direction, storyboard hoặc layout; nếu user cần `.blend` và render, các phần đó vẫn chưa xong. Chỉ chuyển sang mockup 2D như phương án thay thế khi phù hợp phạm vi, và gọi đúng bản chất. Không giao prompt rồi báo “đã dựng 3D”.

## Tích hợp thư viện cá nhân

Hai skill `creative-design-director` và `creative-video-editor` có tài liệu riêng về craft và phản hồi. Nếu chúng có mặt và nhiệm vụ cần, dùng chúng để đi sâu; creative-agency chịu trách nhiệm hệ thiết kế đồ họa event/campaign, độ hoàn chỉnh và tích hợp sản xuất. Không nạp cả hai cho mọi thao tác nhỏ. Khi thiếu skill bổ trợ, vẫn dùng tài liệu [Visual development](visual-development.md) tự chứa; không biến việc chưa có công cụ thành lý do dùng shapes sơ sài hoặc một ảnh AI duy nhất thay toàn bộ thiết kế.

Với feedback lưu trong `creative-design-director/references/user-design-feedback.md`, chỉ lấy thông tin liên quan đến dự án/nhận diện đang làm. Chỉ dẫn người dùng hiện tại thắng thông tin cũ. Không sao chép toàn bộ nhật ký khách hàng vào skill mới và không tự sửa các skill đó.

Không có skill nào thay thế công cụ thực tế, quyền truy cập, bản quyền hay đánh giá của người dùng. Không mô tả có studio/thiết bị/người thật nếu chỉ đang mô phỏng các vai trò bằng agent.
