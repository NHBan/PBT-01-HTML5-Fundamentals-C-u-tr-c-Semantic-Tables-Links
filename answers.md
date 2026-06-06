Cau A1
1 Khi bạn gõ https://shopee.vn vào trình duyệt và nhấn Enter, hãy liệt kê đúng thứ tự ít nhất 5 bước xảy ra (từ DNS lookup đến render).(Nguồn từ Hành trình 0.3s xuyên đại dương)
    1 Request  xuất phát từ laptop->trình duyệt bắt đầu tìm ra IP của shoppe dựa vào DNS
     → đi qua router WiFi nhà trọ
    2→ Qua nhà mạng VNPT → chạy xuyên cáp quang dưới đáy Thái Bình Dương
    3→ Đến data center của Shoppe ở Hà Nội
    4→ Server xử lý: "Minh muốn xem áo phông"
    5→ Response chạy ngược lại: cáp quang → VNPT → router → laptop
    6→ Chrome nhận file HTML, CSS, JS → render ra giao diện →  Thấy mẫu áo phông
2 Trong DevTools của Chrome, tab Network cho thấy thông tin gì?
        tab network cho phép XEM WEBSITE tải những gì (mục 4.3 Chương 1)
Cau A2-Semintic HTML
    Lỗi phần đầu trang: Dùng <div class="header"> thay vì thẻ chuẩn <header>
    Lỗi menu điều hướng: Dùng <div class="menu"> để bọc các đường link chính thay vì dùng thẻ <nav>
    Lỗi vùng nội dung chính: Dùng <div class="main"> thay vì dùng thẻ <main>
    Lỗi khối nội dung sản phẩm: Sản phẩm là một phần nội dung độc lập, nhưng lại đang dùng 
    <div class="product"> thay vì thẻ <article>
    Lỗi phần chân trang: Dùng <div class="footer"> thay vì dùng thẻ <footer>
    Lỗi trong thẻ div cuối cùng:Phần nội dung nên sử dụng &copy thay vì ký tự đặc biệt
    
    CODE SAU KHI SUA

<header>
<div class="logo">ShopTLU</div>
<nav>
    <ul>
        <li><a href="/">Trang chủ</a></li>
        <li><a href="/products">Sản phẩm</a></li>
    </ul>
</nav>
</header>
<main>
<article class="product">
    <h2 class="title">iPhone 16 Pro</h2>
    <div class="price">25.990.000đ</div>
    <div class="image">
        <img src="iphone.jpg" alt="iPhone 16 Pro">
    </div>
</article>
</main>

<footer>
    &copy; 2026 ShopTLU
</footer>
Câu A3 — Block vs Inline
    Không chạy code, hãy vẽ tay (hoặc mô tả bằng text art) kết quả hiển thị của đoạn HTML sau. Giải thích tại sao.
    <div>Hộp 1</div>
    <span>Text A</span>
    <span>Text B</span>
    <div>Hộp 2</div>
    <span>Text C</span>
    <strong>Text D</strong>
    <div>Hộp 3</div>
    Hộp 1 Đây là phần tử block nó sẽ luôn bắt đầu từ dòng mới và chiếu chiều rộng nhiều nhất có thể
    Text A Text B Đây là phần tử inline không xuống dòng mà chỉ chiếm đủ độ rộng
    Hộp 2 
    Text C Text D (Boi dam) vì thẻ strong có mang tính chất quan trong 
    Hộp 3
Câu A4 
<thead>: Đại diện cho phần đầu bảng, được sử dụng riêng để chứa các ô tiêu đề của các cột trong bảng
<tbody>: Đại diện cho phần thân bảng, là nơi chứa toàn bộ nội dung và dữ liệu chính của bảng
<tfoot>: Đại diện cho phần chân bảng, thường được đặt ở cuối để chứa các thông tin tổng kết 
Tại sao lại không nên dùng 
    1HTML5 cung cấp các thẻ để xây dựng bố ccuj nếu sử dụng table thì sẽ phá vơ đi tiêu chuẩn 
    2Sử dụng table sẽ không tốt cho SEO và Accessibility bằng việc sử dụng các thẻ có tên gọi rõ ràng 
    3 Khó tương thích  tương thích với điện thoại dó các thẻ trong table vô cùng cứng ngắt
    4 Nếu như table phức tạp sẽ tốn nhiều thời gian tải trang hơn
    5 Khó cho việc bảo trì và nâng cấp code bởi các thẻ <th>,<tr>,<td> rất nhiều và lặp lại sẽ rất khó cho lập trình viên

Bài B3:
<!DOCTYPE>
<html>
<head>
    <title>Trang web
    <meta charset="utf8"> ,<!--Thieu meta viewport-->
</head>
<body>
    <h1>Welcome to ShopTLU<h1><!--Nên để h1 vào trong thẻ header-->
    <header>
        <nav>
            <a href="home">Trang chủ<a>
            <a href="products">Sản phẩm</a>
        </nav>
    </header>
    
    <main>
        <section>
            <h3>Sản phẩm hot</h3>
            <img src=iphone.jpg>
            <p>iPhone 16 Pro</p>
            <p>Giá: <b>25.990.000đ</p></b><!--Đóng nhầm thẻ giữa p và b-->
            <!--Nên sử dụng thẻ strong cho giá-->
        </section>
        <!-- vì các thẻ này có nội dung riêng biệt nên ưu tiên dùng <article>-->
        <section>
            <h3>Thông tin</h3>
            <table>
                <tr>
                    <td>Tên</td>
                    <td>Giá</td>
                    <!-- ở dòng 28 và 29 nên dùng thẻ <th> để là dòng tiêu đề-->
                </tr>
                <tr>
                    <td>iPhone</td>
                    <td>25tr</td>
                </tr>
            </table>
        </section>
    </main>
    
    <main>
        <p>Sidebar content</p> <!-- ở trong 1 form HTML chỉ nên có một thẻ main để cho các 
        công cụ tìm kiếm có thể dễ dàng tìm kiếm nội dung-->
    </main>
    
    <footer>
        <p>Copyright 2026
            <!-- Thiếu đóng thẻ p </p> và nên thêm icon copy bằng &copy;-->
    </footer>
</body>

bài B4
4.1 Các thẻ được sử dụng trong screenshot là:<div>,<section>,<picture>,<source>,<img>,<a>
Các thẻ mà trang shoppe không sửa dụng là:<artical>,<figure>+<figcaption>
4.2 Các trang trên em chưa tìm thấy thẻ table 
4.3  Thẻ form với action="/timkiem"
method không khai báo nên nó mặc định là Get (Thông tin đẩy lên thanh url)
 <input type="text"> được sử dụng trong form để tìm kiếm

Câu C1:
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Nguyen Hai Ban</title>
</head>

<body>
    <header>
        <p style="text-align: center;">Shoppe</p>
        <nav><!--sU DUNG NAV VI DAY LA DIEU HUONG-->
            <ul>
                <li><a href="#">Trang chu</a></li>
                <li><a href="#"></a>Gioi thieu</li>
                <li><a href="#">Lien he</a></li>
            </ul>
            <div class="search-bar"><!--Thanh tim kiem-->
                <input type="text" placeholder="Vui long nhap san pham ban mong muon">
            </div>
        </nav>
    </header>
    <main>
        <nav>
            <ol class="breadcrumb"><!--boi vi breadcrumb co so thu tu-->
                <li><a href="">Trang chu</a></li>
                <li><a href="">Dien Thoai</a></li>
                <li><a href="">Iphone 16</a></li>
            </ol>
        </nav>
        <div class="list-product"><!-- de hien thi danh sach ca the-->
            <article class="product"><!-- suwr dung article vi day la mot thong tin doc lap-->
                <img src="./screenshots/z7741436415534_64d93c1c5ea8894a4d156701e922819a.jpg" alt=""
                    style="width: 300px;height: 200px;">
                <div class="infor-product"><!--Vi day la phan thong tin la phan doan-->
                    <h1 class="name-product">Iphone 13</h1>
                    <p class="price">
                        <strong>130.000d</strong>
                    </p>
                    <p class="rating">⭐⭐⭐⭐</p>
                    <p class="description">Hang chat luong nhat tg</p>
                </div>
                <button class="add-item">Them vao gio hang</button>
                <div class="product-table-data"><!-- Su dung div o day de boc lay bang thong tin-->
                    <section><!--su dung section de nhan manh thong tin thong so cua may tinh-->
                        <h3>Bang thong so</h3>
                        <table border="1" style="border-collapse: collapse;">
                            <tr>
                                <td>Màn hình</td>
                                <td>6.1 inch, Super Retina XDR</td>
                            </tr>
                            <tr>
                                <td>Chip</td>
                                <td>Apple A18</td>
                            </tr>
                            <tr>
                                <td>Camera sau</td>
                                <td>48MP & 12MP</td>
                            </tr>
                            <tr>
                                <td>RAM</td>
                                <td>8GB</td>
                            </tr>
                        </table>
                    </section>
                </div>
            </article>
            <article class="product"><!-- suwr dung article vi day la mot thong tin doc lap-->
                <img src="./screenshots/z7741436415534_64d93c1c5ea8894a4d156701e922819a.jpg" alt=""
                    style="width: 300px;height: 200px;">
                <div class="infor-product"><!--Vi day la phan thong tin la phan doan-->
                    <h1 class="name-product">Iphone 13</h1>
                    <p class="price">
                        <strong>130.000d</strong>
                    </p>
                    <p class="rating">⭐⭐⭐⭐</p>
                    <p class="description">Hang chat luong nhat tg</p>
                </div>
                <button class="add-item">Them vao gio hang</button>
                <div class="product-table-data"><!-- Su dung div o day de boc lay bang thong tin-->
                    <section><!--su dung section de nhan manh thong tin thong so cua may tinh-->
                        <h3>Bang thong so</h3>
                        <table border="1" style="border-collapse: collapse;">
                            <tr>
                                <td>Màn hình</td>
                                <td>6.1 inch, Super Retina XDR</td>
                            </tr>
                            <tr>
                                <td>Chip</td>
                                <td>Apple A18</td>
                            </tr>
                            <tr>
                                <td>Camera sau</td>
                                <td>48MP & 12MP</td>
                            </tr>
                            <tr>
                                <td>RAM</td>
                                <td>8GB</td>
                            </tr>
                        </table>
                    </section>
                </div>
            </article>
            <article class="product"><!-- suwr dung article vi day la mot thong tin doc lap-->
                <img src="./screenshots/z7741436415534_64d93c1c5ea8894a4d156701e922819a.jpg" alt=""
                    style="width: 300px;height: 200px;">
                <div class="infor-product"><!--Vi day la phan thong tin la phan doan-->
                    <h1 class="name-product">Iphone 13</h1>
                    <p class="price">
                        <strong>130.000d</strong>
                    </p>
                    <p class="rating">⭐⭐⭐⭐</p>
                    <p class="description">Hang chat luong nhat tg</p>
                </div>
                <button class="add-item">Them vao gio hang</button>
                <div class="product-table-data"><!-- Su dung div o day de boc lay bang thong tin-->
                    <section><!--su dung section de nhan manh thong tin thong so cua may tinh-->
                        <h3>Bang thong so</h3>
                        <table border="1" style="border-collapse: collapse;">
                            <tr>
                                <td>Màn hình</td>
                                <td>6.1 inch, Super Retina XDR</td>
                            </tr>
                            <tr>
                                <td>Chip</td>
                                <td>Apple A18</td>
                            </tr>
                            <tr>
                                <td>Camera sau</td>
                                <td>48MP & 12MP</td>
                            </tr>
                            <tr>
                                <td>RAM</td>
                                <td>8GB</td>
                            </tr>
                        </table>
                    </section>
                </div>
            </article>
            <article class="product"><!-- suwr dung article vi day la mot thong tin doc lap-->
                <img src="./screenshots/z7741436415534_64d93c1c5ea8894a4d156701e922819a.jpg" alt=""
                    style="width: 300px;height: 200px;">
                <div class="infor-product"><!--Vi day la phan thong tin la phan doan-->
                    <h1 class="name-product">Iphone 13</h1>
                    <p class="price">
                        <strong>130.000d</strong>
                    </p>
                    <p class="rating">⭐⭐⭐⭐</p>
                    <p class="description">Hang chat luong nhat tg</p>
                </div>
                <button class="add-item">Them vao gio hang</button>
                <div class="product-table-data"><!-- Su dung div o day de boc lay bang thong tin-->
                    <section><!--su dung section de nhan manh thong tin thong so cua may tinh-->
                        <h3>Bang thong so</h3>
                        <table border="1" style="border-collapse: collapse;">
                            <tr>
                                <td>Màn hình</td>
                                <td>6.1 inch, Super Retina XDR</td>
                            </tr>
                            <tr>
                                <td>Chip</td>
                                <td>Apple A18</td>
                            </tr>
                            <tr>
                                <td>Camera sau</td>
                                <td>48MP & 12MP</td>
                            </tr>
                            <tr>
                                <td>RAM</td>
                                <td>8GB</td>
                            </tr>
                        </table>
                    </section>
                </div>
            </article>
            <article class="product"><!-- suwr dung article vi day la mot thong tin doc lap-->
                <img src="./screenshots/z7741436415534_64d93c1c5ea8894a4d156701e922819a.jpg" alt=""
                    style="width: 300px;height: 200px;">
                <div class="infor-product"><!--Vi day la phan thong tin la phan doan-->
                    <h1 class="name-product">Iphone 13</h1>
                    <p class="price">
                        <strong>130.000d</strong>
                    </p>
                    <p class="rating">⭐⭐⭐⭐</p>
                    <p class="description">Hang chat luong nhat tg</p>
                </div>
                <button class="add-item">Them vao gio hang</button>
                <div class="product-table-data"><!-- Su dung div o day de boc lay bang thong tin-->
                    <section><!--su dung section de nhan manh thong tin thong so cua may tinh-->
                        <h3>Bang thong so</h3>
                        <table border="1" style="border-collapse: collapse;">
                            <tr>
                                <td>Màn hình</td>
                                <td>6.1 inch, Super Retina XDR</td>
                            </tr>
                            <tr>
                                <td>Chip</td>
                                <td>Apple A18</td>
                            </tr>
                            <tr>
                                <td>Camera sau</td>
                                <td>48MP & 12MP</td>
                            </tr>
                            <tr>
                                <td>RAM</td>
                                <td>8GB</td>
                            </tr>
                        </table>
                    </section>
                </div>
            </article>
        </div>
        <section class="review"><!--Nhan manh noi dung ve danh gia boi section dc dung cho phan lon-->
            <h3>Danh gia tu khach hang</h3>
            <div class="review-artical"><!-- Coi moi phan danh gia cua nguoi dung la 1 phaanf rieng biet-->
                <figure class="infor-user ml-0">
                    <img src="" alt="" class="avarta">
                    <figcaption class="name-user">Nguyen Van A</figcaption>
                </figure>
                <p class="rating">⭐⭐⭐⭐</p>
                <p class="comment">Hang tot chat luong vo cung</p>
            </div>
            <div class="review-artical"><!-- Coi moi phan danh gia cua nguoi dung la 1 phaanf rieng biet-->
                <figure class="infor-user ml-0">
                    <img src="" alt="" class="avarta">
                    <figcaption class="name-user">Nguyen Van A</figcaption>
                </figure>
                <p class="rating">⭐⭐⭐⭐</p>
                <p class="comment">Hang tot chat luong vo cung</p>
            </div>
            <div class="review-artical"><!-- Coi moi phan danh gia cua nguoi dung la 1 phaanf rieng biet-->
                <figure class="infor-user ml-0">
                    <img src="" alt="" class="avarta">
                    <figcaption class="name-user">Nguyen Van A</figcaption>
                </figure>
                <p class="rating">⭐⭐⭐⭐</p>
                <p class="comment">Hang tot chat luong vo cung</p>
            </div>
        </section>
    </main>
    <footer>
        <p>&copy;Cua hang 3N</p>
        <nav>
            <a href="#" style="margin-right: 20px;color: #333;text-decoration: none;"> Chinh sach </a>
            <a href="#" style="margin-right: 20px;color: black;text-decoration: none;"> Lien he </a>
            <a href="#" style="margin-right: 20px;color: #333;text-decoration: none;">FQA</a>
        </nav>
    </footer>

</body>

</html>