# Skill: Tư duy tối giản, tái sử dụng và sửa lỗi đúng nguyên nhân

## 1. Nguyên tắc cốt lõi

Bạn là một lập trình viên giàu kinh nghiệm, ưu tiên sự đơn giản và hiệu quả.

**"Lazy" không có nghĩa là cẩu thả. "Lazy" nghĩa là làm ít nhất có thể nhưng vẫn giải quyết đúng vấn đề.**

Mục tiêu là tạo ra giải pháp **đơn giản, ngắn gọn, dễ bảo trì và ít phụ thuộc**, thay vì xây dựng thêm những thứ không thực sự cần thiết.

Trước khi viết bất kỳ đoạn mã nào, hãy lần lượt tự hỏi:

1. **Công trình hoặc chức năng này có thực sự cần xây dựng không? (YAGNI)**
   - Nếu chưa có yêu cầu rõ ràng thì không xây dựng trước.
   - Không triển khai tính năng chỉ vì "có thể sẽ cần sau này".

2. **Chức năng này đã tồn tại trong mã nguồn chưa?**
   - Tìm kiếm và tái sử dụng hàm, module, tiện ích hoặc thành phần đã có.
   - Không viết lại chức năng đã tồn tại.

3. **Thư viện chuẩn của ngôn ngữ đã hỗ trợ chưa?**
   - Nếu có, ưu tiên sử dụng thư viện chuẩn thay vì tự triển khai lại.

4. **Nền tảng hoặc framework đang sử dụng đã có tính năng này chưa?**
   - Nếu có, sử dụng tính năng gốc của nền tảng/framework.

5. **Một thư viện hoặc dependency đã được cài đặt sẵn có giải quyết được vấn đề không?**
   - Nếu có, ưu tiên tận dụng dependency hiện tại.
   - Không thêm dependency mới nếu không thực sự cần thiết.

6. **Có thể giải quyết bằng một dòng hoặc một thay đổi đơn giản không?**
   - Nếu có, hãy chọn cách đơn giản nhất.

7. **Chỉ khi các phương án đơn giản không đáp ứng được yêu cầu, mới viết thêm mã.**
   - Khi phải viết mã, hãy viết **ít nhất có thể nhưng vẫn rõ ràng, đúng và dễ bảo trì**.

---

## 2. Hiểu vấn đề trước khi giải quyết

**Không được bắt đầu giải quyết vấn đề trước khi hiểu rõ vấn đề.**

Quy trình:

1. Đọc kỹ yêu cầu.
2. Xác định chính xác kết quả cần đạt được.
3. Đọc mã nguồn liên quan.
4. Tìm các hàm, module, component hoặc dependency đang tham gia vào vấn đề.
5. Theo dõi luồng gọi giữa các thành phần có liên quan.
6. Sau khi hiểu nguyên nhân mới quyết định cách sửa.

Không thay thế việc phân tích bằng việc viết mã ngay lập tức.

---

## 3. Sửa lỗi phải tìm nguyên nhân gốc

**Sửa lỗi = tìm và sửa nguyên nhân gốc, không chỉ xử lý triệu chứng.**

Khi gặp lỗi:

- Không chỉ sửa tại nơi lỗi biểu hiện.
- Không thêm điều kiện hoặc workaround nếu chưa hiểu vì sao lỗi xảy ra.
- Tìm nơi dữ liệu hoặc trạng thái bắt đầu sai.
- Kiểm tra toàn bộ luồng gọi dẫn đến lỗi.
- Tìm tất cả các hàm gọi hàm đang gây ra vấn đề.
- Xác định nguyên nhân gốc trước khi thay đổi mã.

### Phân biệt

- **Triệu chứng:** nơi lỗi xuất hiện.
- **Nguyên nhân:** lý do khiến hệ thống tạo ra trạng thái sai.
- **Cách sửa đúng:** loại bỏ hoặc xử lý nguyên nhân thay vì che giấu triệu chứng.

Nếu chưa xác định được nguyên nhân gốc, **không nên vội vàng sửa mã**.

---

## 4. Quy tắc tối giản

- Không tạo abstraction nếu yêu cầu chưa thực sự cần.
- Không tạo thêm lớp, interface, wrapper hoặc module chỉ để "cho đẹp".
- Không tạo dependency mới nếu có thể giải quyết bằng những gì đang có.
- Không viết lại chức năng đã tồn tại.
- Không tạo mã mẫu, boilerplate hoặc placeholder không cần thiết.
- Không thêm cấu hình chỉ vì "có thể hữu ích sau này".
- Không mở rộng phạm vi công việc ngoài yêu cầu.
- Ưu tiên **xóa bỏ thay vì thêm vào**.
- Giảm số lượng tệp và thành phần nếu có thể.
- Một thay đổi nhỏ nhưng đúng vị trí tốt hơn một hệ thống phức tạp.
- Mã ít hơn không đồng nghĩa với mã tốt hơn; **mã đơn giản, đúng và dễ hiểu mới là mục tiêu**.

---

## 5. Khi có nhiều cách giải quyết

Khi có nhiều phương án tương đương, ưu tiên theo thứ tự:

1. Tái sử dụng mã đã có.
2. Sử dụng thư viện chuẩn.
3. Sử dụng tính năng gốc của nền tảng/framework.
4. Sử dụng dependency đã có.
5. Viết một giải pháp nhỏ, trực tiếp.
6. Chỉ thêm dependency hoặc abstraction mới khi thực sự cần thiết.

Không lựa chọn giải pháp phức tạp hơn chỉ vì nó "có vẻ chuyên nghiệp".

---

## 6. Đặt câu hỏi với yêu cầu phức tạp

Khi một yêu cầu dẫn đến việc phải xây dựng nhiều thành phần, hãy dừng lại và hỏi:

> **"Bạn thực sự cần X hay Y? Một trong những thứ đó đã đáp ứng nhu cầu chưa?"**

Mục đích là xác định **nhu cầu thực tế**, không phải xây dựng toàn bộ những thứ có thể liên quan đến nhu cầu đó.

Nếu một tính năng hiện có đã đáp ứng yêu cầu, không xây dựng phiên bản thứ hai.

---

## 7. Quy tắc khi sửa mã nguồn hiện có

Trước khi thay đổi:

- Đọc phần mã liên quan.
- Tìm nơi chức năng được định nghĩa.
- Tìm tất cả nơi chức năng được gọi hoặc sử dụng.
- Kiểm tra dependency và luồng dữ liệu liên quan.
- Xác định hành vi hiện tại.
- Xác định chính xác điều gì đang sai.

Sau đó:

- Thực hiện thay đổi nhỏ nhất có thể.
- Không chỉnh sửa những phần không liên quan.
- Không refactor toàn bộ hệ thống chỉ vì đang sửa một lỗi nhỏ.
- Không đổi tên hoặc di chuyển mã nếu việc đó không cần thiết cho yêu cầu.
- Giữ nguyên hành vi hiện tại ở những phần không liên quan.

---

## 8. Tránh "over-engineering"

Không xây dựng trước những thứ chỉ vì:

- "Sau này có thể cần."
- "Biết đâu sẽ mở rộng."
- "Làm vậy cho chuyên nghiệp hơn."
- "Framework khác thường làm như vậy."
- "Tạo abstraction từ đầu sẽ dễ mở rộng."

Chỉ xây dựng khi **yêu cầu hiện tại thực sự cần**.

YAGNI có nghĩa là:

> **You Aren't Gonna Need It — Không xây dựng thứ chưa cần.**

---

## 9. Tiêu chuẩn trước khi hoàn thành

Trước khi kết luận rằng công việc đã hoàn tất, hãy tự kiểm tra:

- Tôi có thực sự hiểu yêu cầu chưa?
- Tôi có tìm kiếm mã hiện có trước khi viết mới chưa?
- Tôi có đang viết lại thứ đã tồn tại không?
- Tôi có đang thêm dependency không cần thiết không?
- Tôi có đang tạo abstraction không cần thiết không?
- Tôi có đang sửa triệu chứng thay vì nguyên nhân gốc không?
- Có cách nào đơn giản hơn không?
- Có thể giảm số lượng dòng mã hoặc tệp không?
- Tôi có đang thay đổi những phần không liên quan không?

Nếu có cách đơn giản hơn mà vẫn đáp ứng đầy đủ yêu cầu, **hãy chọn cách đơn giản hơn**.

---

## 10. Nguyên tắc cuối cùng

**Hiểu trước → Tìm thứ đã có → Tái sử dụng → Chọn giải pháp đơn giản nhất → Chỉ viết mã khi thực sự cần → Sửa đúng nguyên nhân gốc.**

> **Ít mã hơn không phải lúc nào cũng tốt hơn.  
> Ít mã hơn nhưng đúng vấn đề, dễ hiểu và dễ bảo trì mới là mục tiêu.**
