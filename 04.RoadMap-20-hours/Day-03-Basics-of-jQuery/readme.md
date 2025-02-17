# A. Basics-of-jQuery

>jQuery là thư viện được viết từ JavaScript, jQuery giúp xây dựng các chức năng bằng Javascript dễ dàng, nhanh và giàu tính năng hơn, code gọn hơn.


Tham khảo 2 nguồn học jQuery:

- Chính chủ: <https://learn.jquery.com/>

- w3School: <https://www.w3schools.com/jquery/jquery_intro.asp>


## ⭐ 1. Tích hợp jQuery vào Html

Dùng link CDN: <https://cdnjs.com/libraries/jquery>

```html
 <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.6.4/jquery.min.js" integrity="sha512-pumBsjNRGGqkPzKHndZMaAG+bir374sORyzM3uulLV14lN5LyykqNk8eEeUlUkB3U0M4FApyaHraT65ihJhDpQ==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
```

Hoặc tải về rồi nhúng vào như file js bình thường.

Để script này vào trước thẻ `</body>` đóng.




##  ⭐ 2. jQuery Selector

Cú pháp: 

```js
$(selector).method();
```

- `$` : dấu $ là ký hiệu để ta khai báo sử dụng Jquery
- selector : chính là các thành phần mình chọn trên trang web. Mình có thể chọn theo id, class, hay tên thẻ.

- method : chính là hành động mà ta tính thực hiện trên phần tử web mà ta đã chọn
Jquery selector được sử dụng để tìm các phần tử trên web dựa vào tên, id, class, type, attribute của một phần tử HTML

Tham khảo: <https://www.w3schools.com/jquery/jquery_ref_selectors.asp>

Danh sách API action: <https://api.jquery.com/>


##  ⭐ 3.  $(document).ready

Trong jQuery phương thức này chứa một callback, nó sẽ thực thi khi mọi thứ đã hoàn thành

```js
$(document).ready(function(){
    console.log("Hello, jQuery!");
});
```


##  ⭐ 4. Tương tác với HTML DOM

### 💥4.1 GET content, giá trị một thuộc tính DOM elements

- html content

Lấy nội dung bên trong thẻ h1

```html
    <h1 class="heading"><span>Hello H1</span></h1>

    <script>
        let content_html = $("h1.heading").html();
        let content_only = $("h1.heading").text();
    </script>
```


- html atributes

Lấy giá trị thuộc tính của Elements

```html
 <a href="https://24h.com.vn" target="_blank">24h.com.vn</a>
 <div class="divClass">Hello Div</div>

 <script>
    // Lấy lên thì phải tạo một biến để hứng kết quả

    let href = $("a").attr("href"); //output: https://24h.com.vn
    //thẻ a làm selector
    //attr() là action, method
    //attr("href") lấy giá trị thuộc tính href

    let divClass = $("div").attr("class"); //output class:  divClass
 </script>

```

- input values

Lấy giá trị của input

```html
    <form id="myForm">
    <input type="text" id="username" name="username" value="Nguyễn Văn A" />

    <input type="checkbox" checked name="isAdmin" value="1">
    <input type="checkbox"  name="isAdmin" value="0">
    </form>

    <script>
        $("#myForm").submit(function(event){
            //Ngăn form submit theo mặc định
            event.preventDefault();

            // Lấy lên thì phải tạo một biến để hứng kết quả
            let username = $("#username").val(); 
            //output : Nguyễn Văn A

            let isAdmin = $("input[name=isAdmin]:checked").val(); 
            //output : 1
            //selector bằng tên của input 

            // Xử lý dữ liệu ở đây (ví dụ: gửi dữ liệu đến server)
            console.log(username,isAdmin);

            // Reset biểu mẫu sau khi gửi thành công
            $("#myForm")[0].reset();
        });
        

    </script>
```

- data attributes

Lấy thuộc tính data trong html5

```html
    <div class="product_item" data-id="123" data-price="200" data-name="iPhone 14 Pro Max">
    ...</div>

    <script>
        let id = $('.product_item').data('id');
        //let id = $('.product_item').attr('data-id');
    </>

```

Lưu ý: Trong các ví dụ trên mỗi ví dụ sử dụng các loại selector khác nhau, nhưng ko có nghĩa với trường hợp đó thì dùng selector đó mà là muốn thể hiện có nhiều cách để selector tới một element.

---

### 💥4.2 SET content, giá trị một thuộc tính DOM elements

- html tags
- input values
- data attributes


>Theo quy tắc lấy lên thế nào thì làm ngược lại là SET

Ví dụ:

```js
    $("#username").val("Nguyễn Thị B");
    //Update input username với giá trị mới
    $("a").attr("href","https://github.com/");
    //Update link thẻ a bằng link mới
    $("h1").html("<p>Welcome to Softech</p>");
```


======================================


## ⭐ 5. CSS Classes

- Doc: <https://api.jquery.com>

```js
    //Thêm một class mới vào element
    $('div').addClass('classname');

    //Xóa một class từ element
    $('div').removeClass('classname');

    //Thêm nếu chưa có hoặc xóa nếu tồn tại class từ element
    $('div').toggleClass('classname');


    //Thêm một thuộc tính css cho element
    //css("propertyname","value");
    $("p").css("background-color", "yellow");


     //Thêm nhiều thuộc tính css cho element
    //css({"propertyname":"value","propertyname":"value",...});
    $("p").css({"background-color": "yellow", "font-size": "200%"});

```

## ⭐ 6. jQuery Effect

```js
 //Ẩn một Element hide(speed,easing,callback)
$('div').hide();

//Hiển thị một elemet đã ẩn
$('div').show();

//https://www.w3schools.com/jquery/jquery_fade.asp
$("#div1").fadeIn();
$("#div2").fadeIn("slow");
$("#div3").fadeIn(3000);

//https://www.w3schools.com/jquery/jquery_slide.asp
$("#panel").slideDown();
```


## ⭐ 7. Events jQuery

- Doc: <https://learn.jquery.com/events/event-basics/>
- Tất cả các sự kiện jQuery nên Chuyển qua dùng on() để thay thế.
- Xem ví dụ: 05.05.Examples\Day-03\jquery-on-method.html


```js
$("p").on("click", function(){
  $(this).hide();
});


$("p").on({
  mouseenter: function(){
    $(this).css("background-color", "lightgray");
  },
  mouseleave: function(){
    $(this).css("background-color", "lightblue");
  },
  click: function(){
    $(this).css("background-color", "yellow");
  }
});
```

## ⭐ 8. AJAX với jQuery

### 8.1  jQuery và phương thức $.get()

Xem ví dụ: 05.Examples\Day-03\jquery-ajax-get.html

### 8.2  jQuery và phương thức $.post()

Xem ví dụ: 05.05.Examples\Day-03\jquery-ajax-post.html

### 8.3 Ajax and Form

==> Nên dùng `fetch` để thay thế Ajax

Doc: <https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API/Using_Fetch>

##  ⭐ 9. C JSON

### 1 JSON là gì ?

- JSON là viết tắt của **J**ava**S**cript **O**bject **N**otation.
- JSON Là một định dạng trao đổi dữ liệu nhẹ nhàng.
- JSON là một văn bản thuần túy được viết như Object của Javascript.
- JSON được sử dụng để gửi dữ liệu giữa các máy tính, dịch vụ I/O.
- JSON là một ngôn ngữ độc lập.

> Lưu ý: Cú pháp JSON bắt nguồn từ ký hiệu Object của JavaScript, nhưng định dạng JSON chỉ là văn bản.



Xem đẩy đủ: <https://www.w3schools.com/js/js_json_intro.asp>

- Tạo một JSON
- Truy cập các phần tử một JSON


### 2 Cú pháp JSON

```js
//JSON
{"name":"John"}
/* 
- key phải là chuổi, và đặt trong dấu nháy kép
- value: kiểu string được đặt trong dấu nháy kép

*/

//Khác so với Javascript
{name:"John"}

```

Giá trị của JSON - JSON Values;

- string

```js
{"name":"John"}
```
- number

```js
{"age":30}
```

- object (json object)

```js
{
"employee":{"name":"John", "age":30, "city":"New York"}
}
```
- array

```js
{
"employees":["John", "Anna", "Peter"]
}
```

- boolean

```js
{"is_admin":true}
```

- null

```js
{"middlename":null}
```

Nó khác Javascript ở chổ là **không bao gồm**: function, date, undefined



### 3 Sử dụng JSON

```js
person = {
"employees":["John", "Anna", "Peter"]
};

//use
let employees = person.employees;

console.log(employees);

```

### 4 Convert một chuổi sang JSON

Ví dụ 1:

```js
// String as JSON:
const str = '{"name":"John", "age":30, "city":"New York"}';
//Convert to JSON
const obj = JSON.parse(str);
```

Ví dụ 2:

```js
//Array as JSON
const text = '["Ford", "BMW", "Audi", "Fiat"]';
const myArr = JSON.parse(text);
```

Ví dụ 3:

```js
const text = '{"name":"John", "birth":"1986-12-14", "city":"New York"}';
const obj = JSON.parse(text);
//Convert a string into a date
obj.birth = new Date(obj.birth);
```

Ví dụ 4:

Hàm ko được hỗ trợ trong JSON tuy nhiên bạn có thể sử dụng theo cách sau:

```js
const text = '{"name":"John", "age":"function () {return 30;}", "city":"New York"}';
const obj = JSON.parse(text);

//Convert a string into a function
obj.age = eval("(" + obj.age + ")");
```


### 5 Convert JSON Object sang JSON string

```js
const myObj = { "name": "John", "age": 31, "city": "New York" };
const myJSON = JSON.stringify(myObj);

//return 
'{"name":"John", "age":31, "city":"New York"}'

```