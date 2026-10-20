## **PHẦN 1: PHÂN TÍCH NGUYÊN NHÂN VÀ BÓC TÁCH BẪY DỮ LIỆU**

### **1. Tại sao định dạng thủ công (In đậm, Phóng to chữ) gây lỗi mục lục trống?**

-   **Bản chất kỹ thuật của Auto TOC (Table of Contents):** Tính năng tạo mục lục tự động trong Microsoft Word hay Google Docs hoạt động dựa trên việc **bóc tách các thẻ phân cấp cấu trúc (Heading Styles)** như `Heading 1`, `Heading 2`, `Heading 3`.
    
-   **Sai lầm của Nam:** Khi Nam chỉ bôi đen chữ, chỉnh tăng kích thước phông (font size 18, 20) và bật in đậm (Bold), văn bản đó về mặt cấu trúc hệ thống **vẫn chỉ là dạng văn bản thường (`Normal` Style)**. Vì không có bất kỳ thẻ `Heading` nào được gán, thuật toán Auto TOC không thể nhận diện được đâu là tiêu đề, dẫn đến thông báo lỗi hệ thống:
    -   **Hậu quả bổ sung:** Việc chỉnh sửa thủ công khiến Nam mất khả năng quản lý định dạng tập trung. Khi cần thay đổi nhận diện (ví dụ đổi màu tiêu đề), Nam phải duyệt và chỉnh sửa bằng tay qua từng trang một thay vì chỉ cần sửa một lần trong cài đặt Style.
    

### **2. Nguyên nhân đoạn văn dài 5 trang bị nhảy vào mục lục**

-   **Bản chất lỗi:** Nam đã bôi đen cả đoạn văn bản 5 trang đó (hoặc đặt con trỏ chuột tại đoạn văn) rồi vô tình nhấn chọn nhãn **`Heading 1`**.
    
-   **Cơ chế quét của Word:** Thuật toán Auto TOC sẽ gom **toàn bộ khối văn bản (paragraph)** mang nhãn `Heading 1` đưa vào bảng mục lục. Do đoạn văn 5 trang bị gán nhãn sai loại, toàn bộ nội dung của 5 trang đó đã bị hiển thị trọn vẹn trong bảng mục lục, làm phá vỡ hoàn toàn cấu trúc tài liệu.
    

## **PHẦN 2: QUY TRÌNH KỸ THUẬT SỬA LỖI VÀ TẠO AUTO TOC CHUẨN**

**1.Bước 1: Chuẩn hóa nhãn (Style Mapping) cho khung tài liệu SRS:**Khôi phục phân cấp dữ liệu từ Normal sang Heading chuẩn.

Thực hiện gán lại nhãn Heading cho các phần trong tài liệu theo đúng phân cấp logic:

-   **Tháo nhãn Heading 1 khỏi đoạn văn 5 trang:** Bôi đen toàn bộ đoạn văn 5 trang bị lỗi, trên thanh công cụ _Home_, chọn nhãn **`Normal`** để đưa văn bản về dạng đoạn văn chuẩn.
    
-   **Gán nhãn Cấp 1 (`Heading 1`):** Áp dụng cho các chương/mục lớn nhất.
    
    -   `1. Giới thiệu` Chọn Heading 1
        
    -   `2. Yêu cầu chức năng`  Chọn Heading 1
        
-   **Gán nhãn Cấp 2 (`Heading 2`):** Áp dụng cho các tính năng con bên trong.
    
    -   `2.1. Đăng ký/Đăng nhập sinh viên`  Chọn Heading 2
        
    -   `2.2. Tìm kiếm & Chọn món ăn`  Chọn Heading 2
        
    -   `2.3. Đặt hàng & Thanh toán`  Chọn Heading 2
        

**2.Bước 2: Tạo Bảng mục lục tự động (Auto TOC):**Chèn mục lục động dựa trên các thẻ Heading vừa gán.

1.  Đặt con trỏ chuột tại trang đầu tiên (sau trang bìa) nơi muốn hiển thị mục lục.
    
2.  Truy cập thẻ **`References`** trên thanh Ribbon.
    
3.  Chọn **`Table of Contents`**  Chọn biểu mẫu **`Automatic Table 1`** (hoặc **`Automatic Table 2`**).
    
4.  Hệ thống sẽ tự động quét toàn bộ các tiêu đề `Heading 1`, `Heading 2` vừa thiết lập và xuất ra bảng mục lục chuẩn cấu trúc.
    

**3.Bước 3: Cập nhật mục lục (Update TOC) khi thay đổi nội dung:**Xử lý sự cố lệch số trang sau khi gõ thêm văn bản.

Khi Nam gõ thêm nội dung tài liệu khiến các mục bị đẩy sang trang mới, số trang trên mục lục sẽ bị lệch. Thực hiện đồng bộ lại theo các thao tác:

1.  Nhấp chuột phải vào bảng mục lục Auto TOC vừa tạo.
    
2.  Chọn **`Update Field`** (hoặc nhấn phím tắt **`F9`**).
    
3.  Hộp thoại hiện ra với 2 lựa chọn:
    
    -   **`Update page numbers only`:** Chỉ cập nhật lại số trang (dùng khi chỉ gõ thêm văn bản mà không thêm/xóa tiêu đề).
        
    -   **`Update entire table`:** Cập nhật toàn bộ cả số trang lẫn tiêu đề mới (khuyên dùng để đảm bảo đồng bộ 100%).
        
4.  Nhấn **OK** để hoàn tất.




