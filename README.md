---
title: "Thiết kế Nội thất Biệt thự Hiện Đại Vinhomes Riverside - Anh Khoa"
description: "Dự án thiết kế và thi công nội thất biệt thự phong cách Modern Luxury sử dụng gỗ óc chó tự nhiên cao cấp tại Vinhomes Riverside."
date: 2024-03-15T10:00:00+07:00
draft: false
thumbnail: "/img/du-an/vinhomes-riverside/anh-dai-dien.jpg" # Đường dẫn đến ảnh đại diện dự án
image_alt: "Không gian phòng khách biệt thự Vinhomes Riverside gỗ óc chó"

# --- Thông tin Meta Box cho Dự Án ---
chu_dau_tu: "Anh Khoa"
dia_chi_thi_cong: "Vinhomes Riverside, Long Biên, Hà Nội"
loai_hinh: "Biệt thự Song lập"
phong_cach: "Hiện đại Sang trọng (Modern Luxury)"
vat_lieu_chinh: "Gỗ Tự Nhiên Óc Chó Bắc Mỹ, Đá tự nhiên, Da nhập khẩu"
don_vi: "ROMAX"
tong_dien_tich_xd: "280 m2"
nam_thuc_hien: "2023"

# --- Metadata SEO (Tùy chọn) ---
title_seo: "Thiết Kế Nội Thất Biệt Thự Óc Chó Vinhomes Riverside | ROMAX 2023"
description_seo: "Tham khảo dự án thiết kế thi công nội thất biệt thự Vinhomes Riverside phong cách hiện đại sang trọng, vật liệu gỗ óc chó tự nhiên. Thực hiện bởi ROMAX năm 2023."

tags: ["du-an", "biet-thu", "hien-dai", "go-oc-cho", "vinhomes"]
# series: ["Tên Series Nếu Có"]
# series_order: 1
---


Nội dung chi tiết về dự án viết ở đây...

<!-- Chèn ảnh bằng Markdown -->
![Phòng khách dự án Vinhomes Riverside](/img/du-an/vinhomes-riverside/phong-khach.jpg)

![Phòng bếp hiện đại](/img/du-an/vinhomes-riverside/phong-bep.jpg)
Ok, để hiển thị ảnh thumbnail với tỷ lệ 4:3 cho các trang danh sách/danh mục (sử dụng layout card mặc định) và cho trang danh sách của section `noi-that`, bạn cần cấu hình trong file `config.toml` (hoặc `hugo.toml`, `config/params.toml` tùy cấu trúc dự án của bạn).

Đây là cách cấu hình **khuyến nghị và đúng theo thiết kế của theme **:

**Trong file `config.toml` (hoặc tương đương):**

Tìm đến mục `[params.sections]` và thêm hoặc sửa các cấu hình cho từng section/taxonomy bạn muốn áp dụng tỷ lệ 4:3.

```toml
# config.toml hoặc hugo.toml hoặc config/_default/params.toml

[params]
  # ... các cấu hình khác của bạn ...

  [params.sections]
    # Cấu hình cho section 'noi-that'
    [params.sections.noi-that]
      layout = "card"  # Đảm bảo đang dùng layout card nếu bạn muốn
      cols = 3         # Ví dụ: số cột hiển thị card
      ratio = "4x3"    # <- Đây là dòng quan trọng để đặt tỷ lệ 4:3
      # Các cấu hình khác cho list view của noi-that nếu cần
      # header = "full"
      # footer = "none"
      # ...

    # Cấu hình cho taxonomy 'categories' (trang /categories/ và /categories/ten-danh-muc/)
    [params.sections.categories]
      layout = "card"
      cols = 3
      ratio = "4x3"    # <- Đặt tỷ lệ 4:3 cho trang danh sách category
      # ...

    # Cấu hình cho taxonomy 'tags' (trang /tags/ và /tags/ten-the/)
    [params.sections.tags]
      layout = "card"
      cols = 3
      ratio = "4x3"    # <- Đặt tỷ lệ 4:3 cho trang danh sách tag
      # ...

    # Cấu hình cho các section khác nếu cần (ví dụ: blog)
    # [params.sections.blog]
    #   layout = "card"
    #   cols = 3
    #   ratio = "4x3"
    #   # ...

```

**Giải thích:**

1.  **`[params.sections]`**: Đây là nơi theme  cho phép bạn định nghĩa các cấu hình riêng cho cách hiển thị trang danh sách của từng section hoặc taxonomy.
2.  **`[params.sections.noi-that]`**: Cấu hình cụ thể cho section có tên `noi-that`. Khi Hugo render trang danh sách `/noi-that/`, nó sẽ sử dụng các thông số tại đây.
3.  **`[params.sections.categories]`, `[params.sections.tags]`**: Tương tự, cấu hình cho các trang liệt kê của taxonomy `categories` và `tags`.
4.  **`ratio = "4x3"`**: Dòng này chỉ định rõ ràng rằng các card trong trang danh sách của section/taxonomy tương ứng sẽ sử dụng ảnh thumbnail với tỷ lệ 4:3. Partial `partials/assets/section-list.html` sẽ đọc giá trị này và truyền nó xuống cho partial `partials/assets/card.html`, sau đó `partials/assets/image.html` sẽ sử dụng tỷ lệ này để xử lý ảnh.
5.  **`layout = "card"`**: Đảm bảo rằng bạn đang sử dụng layout dạng card để các cấu hình `ratio` này có hiệu lực đúng như mong đợi với cấu trúc card.
6.  **`cols = 3`**: Đây là ví dụ, bạn có thể điều chỉnh số cột theo ý muốn.

**Cách hoạt động:**

*   Khi render trang danh sách (ví dụ `/noi-that/` hoặc `/categories/`), Hugo sẽ dùng layout `_default/list.html`.
*   Layout này gọi `partials/assets/section-list.html`.
*   `section-list.html` sẽ kiểm tra `config.toml` xem có cấu hình riêng cho section/taxonomy hiện tại không (`params.sections.noi-that`, `params.sections.categories`,...).
*   Nếu tìm thấy `ratio = "4x3"`, nó sẽ truyền giá trị này xuống cho `card-group.html` -> `card.html`.
*   `card.html` nhận được `ratio="4x3"` và truyền nó cho `image.html`.
*   `image.html` và các helper của nó sẽ sử dụng tỷ lệ `4x3` để chọn kích thước phù hợp (từ `data/dam/dimensions.yaml` hoặc mặc định) và áp dụng phương thức xử lý ảnh (thường là `Fill` khi có ratio) để tạo thumbnail đúng tỷ lệ 4:3.

**Lưu ý:**

*   Sau khi thay đổi `config.toml`, hãy **khởi động lại Hugo server** (`hugo server`) để thay đổi có hiệu lực.
*   Nếu bạn không định nghĩa kích thước cụ thể cho tỷ lệ "4x3" trong file `data/dam/dimensions.yaml`, Hugo sẽ sử dụng kích thước mặc định được định nghĩa trong `partials/assets/helpers/GetDimension.html` (là `1400x1050` cho `4x3`).
*   Phương pháp cấu hình qua `config.toml` này tốt hơn là sửa trực tiếp code của các partials (`card.html` hay `section-list.html`) vì nó giữ cho theme gốc ít bị thay đổi hơn và dễ quản lý cấu hình cho từng section riêng biệt.

Chào bạn, dựa trên các file code bạn đã cung cấp và cách theme  xử lý ảnh, việc hiển thị thumbnail (kích thước và tỷ lệ) sẽ khác nhau tùy thuộc vào ngữ cảnh và cấu hình:

**Tóm tắt chung:**

*   Theme  sử dụng partial `partials/assets/image.html` và các partial con helper (`helpers/image-dimension.html`, `helpers/image-set.html`, `helpers/GetDimension.html`) để xử lý và tạo các phiên bản ảnh với kích thước khác nhau.
*   Nó có thể sử dụng các phương thức xử lý ảnh tích hợp của Hugo (`.Resize`, `.Fill`, `.Fit`) hoặc dựa vào các dịch vụ CDN ảnh như Cloudinary, ImageKit nếu được cấu hình.
*   **Tỷ lệ (Ratio):** Có thể được chỉ định trực tiếp trong front matter (`thumbnail: { url: "...", ratio: "16x9" }`), trong cấu hình section (`config.toml`), trong code của partial (ví dụ: `card.html` có tỷ lệ mặc định), hoặc được xác định tự động dựa trên ảnh gốc.
*   **Kích thước (Dimensions):** Các kích thước cụ thể thường được định nghĩa sẵn cho các tỷ lệ phổ biến (ví dụ: 16:9, 4:3) trong file `data/dam/dimensions.yaml` (nếu có) hoặc sử dụng các giá trị mặc định trong `partials/assets/helpers/GetDimension.html`. Kích thước cuối cùng cũng phụ thuộc vào phương thức xử lý (Fill, Fit, Resize).
*   **Phương thức xử lý:**
    *   `Fill`: Thay đổi kích thước ảnh để lấp đầy chính xác kích thước yêu cầu, có thể cắt bớt phần thừa để giữ đúng tỷ lệ.
    *   `Fit`: Thay đổi kích thước ảnh để vừa khít *trong* kích thước yêu cầu mà không cắt ảnh, giữ nguyên tỷ lệ gốc. Chiều rộng hoặc chiều cao cuối cùng có thể nhỏ hơn kích thước yêu cầu.
    *   `Resize`: Thay đổi kích thước ảnh đến một chiều cụ thể (ví dụ `800x` nghĩa là rộng tối đa 800px), giữ nguyên tỷ lệ gốc.

**Chi tiết cho từng trường hợp:**

1.  **Trang đơn (Single Page - `_default/single.html`):**
    *   Sử dụng partial `partials/single/thumbnail.html`.
    *   Partial này gọi `partials/assets/image.html`.
    *   **Tỷ lệ:** Ưu tiên lấy từ `Params.Thumbnail.ratio` trong front matter. Nếu không có, nó sẽ lấy từ `site.Params.thumbnails.ratio` trong `config.toml`. Nếu cả hai đều không có, **mặc định là "21x9"**.
    *   **Kích thước:** Được xác định bởi các kích thước định nghĩa sẵn cho tỷ lệ được chọn (trong `data/dam/dimensions.yaml` hoặc helper defaults).
    *   **Phương thức:** Sử dụng `.Fill` (vì tỷ lệ được xác định), ảnh sẽ được resize và cắt để khớp chính xác với tỷ lệ và kích thước đích.
    *   **File:** `partials/single/thumbnail.html`, `partials/assets/image.html`, `partials/assets/helpers/image-dimension.html`, `partials/assets/helpers/GetDimension.html`.

2.  **Trang đơn tùy chỉnh (Single Page - `noi-that/single.html` - Ảnh đại diện chính):**
    *   Code trong `noi-that/single.html` gọi trực tiếp `resources.Get(src).Resize("800x")`.
    *   **Tỷ lệ:** Giữ nguyên tỷ lệ gốc của ảnh.
    *   **Kích thước:** Chiều rộng tối đa là 800px, chiều cao tự động điều chỉnh theo tỷ lệ gốc.
    *   **Phương thức:** `.Resize`.
    *   **File:** `layouts/noi-that/single.html`.

3.  **Bài viết liên quan (Related Posts - `noi-that/related-posts.html`):**
    *   Code trong `noi-that/related-posts.html` gọi `resources.Get(src).Fill("400x300")`.
    *   **Tỷ lệ:** Cố định là **4:3**.
    *   **Kích thước:** Cố định là **400px x 300px**.
    *   **Phương thức:** `.Fill`. Ảnh sẽ được resize và cắt để vừa khít 400x300.
    *   **File:** `partials/noi-that/related-posts.html`.

4.  **Trang danh sách/danh mục (List/Taxonomy - `_default/list.html` - Hiển thị dạng Card):**
    *   Sử dụng `partials/assets/section-list.html` -> `partials/assets/card-group.html` -> `partials/assets/card.html`.
    *   `card.html` gọi `partials/assets/image.html`.
    *   **Tỷ lệ:** Rất linh hoạt, phụ thuộc vào cấu hình:
        *   Ưu tiên 1: `ratio` trong cấu hình của section đó trong `config.toml` (`site.Params.sections.<section_name>.ratio`).
        *   Ưu tiên 2 (Nếu không có cấu hình ratio):
            *   Với `orientation: stacked` (mặc định): Tỷ lệ mặc định là **16:9**.
            *   Với `orientation: horizontal` hoặc `horizontal-sm`: Tỷ lệ mặc định là **1:1**.
    *   **Kích thước:** Được xác định bởi các kích thước định nghĩa sẵn cho tỷ lệ được chọn.
    *   **Phương thức:** Thường là `.Fill` vì tỷ lệ thường được xác định (hoặc có mặc định).
    *   **File:** `partials/assets/section-list.html`, `partials/assets/card-group.html`, `partials/assets/card.html`, `partials/assets/image.html`.

5.  **Ảnh nổi bật (Featured Image - Trang chủ hoặc List page có layout="featured"):**
    *   Sử dụng `partials/list/featured.html` -> `partials/list/featured-illustration.html`.
    *   `featured-illustration.html` gọi `partials/assets/image.html`.
    *   **Tỷ lệ:** Hardcoded trong `featured-illustration.html` là **16:9**.
    *   **Kích thước:** Được xác định bởi các kích thước định nghĩa sẵn cho tỷ lệ 16:9.
    *   **Phương thức:** `.Fill`.
    *   **File:** `partials/list/featured.html`, `partials/list/featured-illustration.html`, `partials/assets/image.html`.

**Lưu ý quan trọng:**

*   **Cấu hình:** Kích thước và tỷ lệ trong các trường hợp linh hoạt (như card trong list page) phụ thuộc nhiều vào cấu hình trong `config.toml` (ví dụ `site.Params.sections.<section_name>.*`) và file `data/dam/dimensions.yaml` (nếu bạn tạo và sử dụng nó).
*   **Image Provider:** Nếu bạn cấu hình sử dụng CDN ảnh (Cloudinary, ImageKit), các partial adapter tương ứng (`partials/assets/adapters/*.html`) sẽ đảm nhận việc tạo URL với các tham số biến đổi kích thước/tỷ lệ theo cú pháp của CDN đó, thay vì dùng hàm của Hugo. Kết quả cuối cùng vẫn dựa trên tỷ lệ và kích thước đã được xác định.
*   **Ảnh SVG:** Ảnh SVG thường không được resize mà chỉ được nhúng trực tiếp.

Hy vọng giải thích chi tiết này giúp bạn hiểu rõ hơn về cách thumbnail được xử lý trong theme !