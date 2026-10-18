# 3D, không gian sự kiện và visual LED

Dùng khi brief có hình khối 3D, phối cảnh, sân khấu, màn hình đặc biệt, projection mapping hoặc nội dung biểu diễn. Đây là quy trình thiết kế và phối hợp sản xuất; bản phối cảnh không thay thế hồ sơ kết cấu, điện, tải treo hay nghiệm thu của đơn vị có chuyên môn. Không hứa “chạy được trên mọi LED”.

## 1. Hồ sơ kỹ thuật cho LED/mapping/sân khấu

Phần này và các gate playback/hiện trường chỉ áp dụng khi có hệ màn hình hoặc không gian sự kiện. Với 3D sản phẩm, logo hoặc scene độc lập, đi đến pipeline ở mục 2 và lấy spec render/file theo brief; không yêu cầu pixel map, cue hoặc operator không liên quan.

Producer lấy dữ liệu từ người phụ trách LED/playback, ghi người xác nhận và phiên bản:

| Nhóm | Thông tin phải có |
|---|---|
| Không gian | Mặt bằng/mặt đứng; đơn vị đo; kích thước, góc, cao độ từng bề mặt; khoảng hở; vật che; vị trí khán giả và camera. |
| Pixel | ID màn; pixel W×H từng mặt; pitch; hướng lắp; canvas nội dung; canvas tín hiệu; tọa độ từng vùng; vùng trống/mask/crop. |
| Playback | Phần mềm/phiên bản, máy phát, processor; codec/container được nhận; giới hạn kích thước, băng thông, layer đồng thời; có realtime hay prerender. |
| Thời gian | FPS chính xác của nguồn, timeline, đầu ra; progressive/interlaced; duration theo frame; timecode và cách đánh số DF/NDF khi dùng; trigger, hold, loop, out. |
| Màu/alpha | Không gian màu, transfer/gamma, range, bit depth; ai thực hiện transform/LUT; alpha cần hay không, straight/premultiplied; mẫu file đã chạy thử. |
| Show | Run of show, cue ID, người gọi cue, tín hiệu nhận cue, âm thanh, IMAG, ánh sáng, file dự phòng, lịch tổng duyệt. |

Không suy pixel canvas từ số mét hoặc tự quy toàn bộ về 16:9. Pitch và kích thước cho phép ước tính, nhưng bản đồ pixel của vendor mới là cơ sở xuất. Phân biệt sơ đồ các màn đặt ngoài đời, canvas sáng tác và canvas tín hiệu mà processor nhận. Chúng có thể bố trí khác nhau. [Resolume Input Maps](https://resolume.com/support/en/input-maps)

Ghi rõ 30000/1001 nếu đó là tốc độ đã chốt; không làm tròn thành 30. “LED refresh rate” của phần cứng không tự quyết định FPS nội dung. Đối chiếu chuỗi tín hiệu với kỹ thuật viên. [Resolume Screens](https://resolume.com/support/screens)

**Thiếu packet:** tạo bảng `Đã xác nhận / Giả định / Còn thiếu / Người cung cấp / Hạn cần`. Tiếp tục moodboard, KV, storyboard, blockout, styleframe và preview có nhãn giả định. Chỉ giữ lại bước khóa pixel map, render cuối hoặc bàn giao show tương ứng với dữ liệu còn thiếu; không dừng toàn bộ sáng tạo. Kích thước preview chỉ phục vụ duyệt ý tưởng, không gọi là thông số giao.

## 2. Pipeline 3D theo quyết định có thể duyệt

1. **Art direction:** viết mục đích của 3D: làm rõ sản phẩm, xây biểu tượng, tạo chiều sâu hoặc kể chuyển động. Chọn mức stylized/photoreal dựa trên thương hiệu, ngân sách và thời gian. Reference phải ghi nguồn, điểm học hỏi và giới hạn sử dụng.
2. **Blockout:** dựng hình đơn giản, tỷ lệ, camera, tiêu cự, silhouette và khoảng dành cho chữ. Duyệt bằng clay render ở góc chính và các crop cần dùng. Kiểm tra chuyển động camera bằng animatic trước khi đầu tư vật liệu.
3. **Asset:** lập danh mục tự dựng/mua/khách cung cấp; lưu license. Kiểm tra đơn vị, transform, normals, UV, texel density phù hợp khoảng nhìn; giữ logo/chữ chuẩn từ nguồn vector. Chọn mức topology theo deformation và khoảng cách camera, không tăng polygon vô điều kiện.
4. **Look development:** so vật liệu dưới ánh sáng trung tính rồi ánh sáng nghệ thuật; kiểm soát roughness, phản xạ, độ trong, tỷ lệ texture. Chốt mẫu màu sản phẩm với người có thẩm quyền. Duyệt silhouette, key light, separation và vùng chữ trước chi tiết phụ.
5. **Animation:** chốt nhịp vào–giữ–ra, trọng lượng, điểm nhấn và chuyển cảnh. Bake/cache simulation cần thiết, giữ seed và phiên bản. Kiểm tra frame đầu/cuối, vùng bị cắt và các frame cực trị; camera đẹp ở một frame chưa chứng minh cả shot ổn.
6. **Render:** thử frame nặng nhất và đoạn chuyển động đại diện; ước tính thời gian từ số đo thực, cộng ngân sách sửa. Dùng image sequence khi cần phục hồi frame lỗi; giữ render master riêng bản playback. Không render cả phim trước khi test pipeline đạt.
7. **Composite:** chọn pass phục vụ sửa thực tế, chẳng hạn beauty, depth, shadow, object/material masks; không xuất mọi pass theo thói quen. Render passes cung cấp dữ liệu tách biệt; Cryptomatte hỗ trợ cô lập đối tượng/vật liệu. [Blender Passes](https://docs.blender.org/manual/en/latest/render/layers/passes.html)

Ghi working space, input texture space, view transform và output transform ngay từ styleframe. Dữ liệu màu, normal và displacement phải được diễn giải đúng loại. Render/composite scene-linear và màu hiển thị là các bước khác nhau; không bake transform rồi áp lại ở phần mềm kế tiếp. Chạy một frame xuyên suốt render → composite → encode → player để so màu, alpha và clipping. [Blender Color Spaces](https://docs.blender.org/manual/en/5.1/render/color_management/color_spaces.html)

## 3. Thiết kế nội dung cho sân khấu

Lập content matrix theo khoảnh khắc: đón khách, countdown, mở màn, phát biểu, giới thiệu người, chuyển tiết mục, trao giải, kết thúc, standby. Mỗi mục nêu thông điệp, mức năng lượng, vùng dành cho người thật/chữ/IMAG, âm thanh và chế độ phát. Tránh để mọi cue đều có chuyển động mạnh; nền phát biểu phải hỗ trợ người nói.

Tạo stage preview đúng tương quan các mặt, đồng thời giữ file pixel map có số tọa độ rõ ràng. Xem cả góc khán giả xa, lệch trục và camera. Không đặt tên người, logo hoặc nội dung bắt buộc qua đường ghép, khoảng hở hay vùng người đứng che. Safe area lấy từ điều kiện thực và thiết kế mapping, không áp một phần trăm chung.

Với nhiều màn, chọn rõ: một hình liên tục; từng màn độc lập; hay nền liên tục kèm vùng thông tin riêng. Test hình tròn, grid, ID màn, mũi tên và đường nối để phát hiện kéo méo, đảo chiều, sai crop. Giữ test pattern riêng khỏi thư mục cue chương trình.

**Anamorphic:** ghi tọa độ/chiều cao điểm nhìn mục tiêu và hình học màn. Dựng scene từ camera đó, duyệt cả góc mục tiêu lẫn lệch trục; nếu ưu tiên camera quảng bá thay cho toàn khán phòng, nói rõ đánh đổi. Hiệu ứng đúng phối cảnh phụ thuộc eyepoint, không bảo đảm “3D nổi” từ mọi vị trí. [Disguise Mesh Mapping](https://help.disguise.one/designer/mapping/mapping-types/mesh-mapping)

Loop phải chuyển liền ở ranh giới thời gian: kiểm tra vị trí, vận tốc, ánh sáng, hạt và âm thanh. Tránh lặp trùng frame đầu ở cuối gây khựng. Tách intro–loop–out khi thời lượng sân khấu khó đoán; xác định operator sẽ giữ, thoát ngay hay đợi điểm thoát. Không chọn duration cố định khi run of show yêu cầu linh hoạt.

## 4. Kiểm tra và bàn giao

| Gate | Bằng chứng để qua |
|---|---|
| Ý tưởng | Styleframe + stage mockup + lý do phù hợp brief; rõ phần nào chỉ minh họa. |
| Kỹ thuật | Packet được xác nhận; pixel map có phiên bản; file mẫu decode, mapping và màu đúng trên hệ nhận. |
| Nội dung | Đúng tên, dấu tiếng Việt, logo, thứ tự sponsor; chữ đọc được ở góc/khoảng cách mục tiêu. |
| Chuyển động | Không pop, flicker, frame thiếu, simulation lỗi, nhòe chữ hoặc loop giật; cue vào/ra đúng. |
| Hiện trường | Playback toàn tải; đồng bộ âm thanh/camera khi cần; test chuyển cue, standby và file dự phòng; ghi người nghiệm thu. |

Không quy định một codec cho mọi server. Nếu vendor dùng Resolume và yêu cầu DXV, lựa chọn alpha phải khớp nguồn; tùy chọn “With Alpha” không tự xóa nền. Lợi ích tăng tốc DXV không mặc định áp dụng cho phần mềm khác. [Resolume DXV](https://resolume.com/support/en/rendering-to-dxv)

Alpha phải được xem trên nền sáng và tối để phát hiện viền. Kiểm tra codec/container thực bằng metadata và mở thử trên máy đích; phần mở rộng `.mov` chưa đủ mô tả file. Giữ bản preview nhẹ có watermark phiên bản riêng với master phát.

Bàn giao gồm manifest, thumbnail/contact sheet, cue sheet, thông số xuất, map/mask, file phát, backup và source theo phạm vi thỏa thuận. Cue sheet có `cue_id | asset/version | màn đích | duration/frame_count | fps | trigger | loop/hold | out | audio | fallback`. Chỉ định bản được duyệt; không ghi đè file đã duyệt bằng nội dung khác cùng tên. Ghi thay đổi sau tổng duyệt và kiểm lại cue bị ảnh hưởng.

## 5. Phối hợp vật phẩm in và không gian

Hỏi vendor về kích thước thành phẩm, tỷ lệ file, chất liệu, cách nối tấm, cắt/bế/gấp, vùng khoan/treo, bleed, profile màu, ảnh tại kích thước thực và định dạng nhận. Không mặc định 300 ppi, CMYK profile hoặc bleed cho tất cả backdrop, standee, decal, hộp và vật thể. Adobe phân biệt bleed với vùng trim và khuyên hỏi nhà in về lượng bleed phù hợp. [Adobe Marks & Bleeds](https://helpx.adobe.com/illustrator/using/printers-marks-bleeds.html)

Kiểm tra artboard, đơn vị và tỷ lệ ghi trên bản vẽ; tách đường kỹ thuật khỏi artwork theo quy ước vendor. So proof/mẫu chất liệu khi màu thương hiệu hoặc gia công quan trọng. Phối cảnh chỉ chứng minh ý đồ: độ bền, tải, chống cháy, điện và lối thoát do đội chuyên môn xác nhận trước thi công.

Nguồn được đối chiếu ngày **2026-10-16**. Đây là quy trình tổng hợp; thông số dự án và tài liệu đúng phiên bản thiết bị luôn cần được xác nhận lại.
