
﻿<h2>1.Cách sử dụng Postman: biến môi trường, biến sẵn có của postman, import, export. </h2>
POSTMAN là một App Extensions, cho phép làm việc với các API giúp ích rất nhiều cho việc testing. Hỗ trợ tất cả các phương thức HTTP (GET, POST, PUT, DELETE, OPTIONS, HEAD ...)<br>
POSTMAN cho phép lưu lại lịch sử các lần request, rất tiện cho việc sử dụng lại khi cần.<br>
<h3>Cài đặt </h3>
Để bắt đầu với POSTMAN, bạn truy cập vào trang chủ https://www.getpostman.com/ và download phiên bản phù hợp cho hệ điều hành đang sử dụng (có các phiên bản cho MAC OS, Windows 32bit, Window 64bit).<br>
    <img src="https://i.imgur.com/1DHjpTq.png"><br><br>
Sau khi tải về bạn tiến hành cài đặt bình thường và có thể sử dụng ngay.Bạn mở app lên giao diện .<br><br>
     <img src="https://i.imgur.com/6ZbkA66.png">  <br><br>
Như vậy là bạn có thể sử dụng POSTMAN rồi nhé. <br>
<h3>Các chức năng cơ bản</h3>
+ Cho phép gửi HTTP Request với các method GET, POST, PUT, DELETE.<br>
+ Cho phép post dữ liệu dưới dạng form (key-value), text, json<br>
+ Hiện kết quả trả về dạng text, hình ảnh, XML, JSON<br>
+ Cho phép thay đổi header của các request<br>
<h3> Sử dụng</h3>
Cách sử dụng Postman rất đơn giản, bạn chỉ việc điền Url của Api, chọn phương thức Get, Post... thêm các parameter cần thiết và ấn Send.<br>
Ví dụ ta lấy dữ liệu từ Server sử dụng method GET<br><br>
     <img src="https://i.imgur.com/i9UPvTm.png"> <br><br>
<h3>Biến môi trường trong Postman</h3>
Khi làm API, chúng ta thường có 3 môi trường, local, staging, production, mỗi môi trường sẽ có 1 base_url riêng nên khi test API trên cả 3 môi trường chúng ta phải tạo ra 3 request với thông số giống hệt nhau, chỉ khác mỗi base_url ==> gây một số bất tiện khi test API.<br>
Để giải quyết vấn đề trên, POSTMAN cung cấp cho chúng ta tùy chọn Environments Variable<br>
Environments variable cho phép ta cài đặt các biến môi trường, sau đó trong mỗi môi trường ta có thể lấy biến đó ra với nội dung riêng biệt.<br>
Ví dụ tạo tài khoản demo trên 2 môi trường ta có 2 url sau:<br>
+ Staging: http://lechinh.com/api/demo<br>
+ Local: http://localhost:1996/api/demo<br>
 Ta vào New chọn Environments giao diện sẽ hiện lên và ta tạo môi trường đặt tên là staging và local<br><br>
     <img src="https://i.imgur.com/6aGXjMT.png"> <br><br>
Bây giờ tạo 2 base_url cho 2 môi trường staging, local<br>
Staging: base_url = http://lechinh.com<br>
Local: base_url = http://localhost:1996<br><br>
  <img src="https://i.imgur.com/W6Q3ISc.png"> <br><br><br>
  <img src="https://i.imgur.com/trMM1YA.png"><br><br>
Sau đó, trong link gọi Web API, ta chỉ việc gọi biến base_url và đặt nó trong ngoặc nhọn {{}} là xong.<br><br>
   <img src="https://i.imgur.com/l4jQRRN.png"> <br>
Biến môi trường sẽ được sử dụng mọi nơi trong url, header, body...<br>
Bây giờ mỗi khi muốn test trên từng môi trường, bạn chỉ cẩn chuyển đổi qua lại các môi trường mà ko cần phải thay đổi đường dẫn url hoặc bất kì chỗ nào khác nếu bạn có sử dụng biến.<br><br>
   <img src="https://i.imgur.com/GRHSmjC.png"> <br>
<h3>Export trong Postman</h3>
Collection: Collection là một tập hợp của nhiều request. Những request liên quan tới nhau thì ta gom lại vào chung 1 collection để dễ quản lý hơn.<br>
Với mỗi dự án thì ta sẽ tạo 1 Collection riêng. Để share Collection với các thành viên khác trong team ta có thể với mỗi Collection ta export nó ra file json sau đấy gửi cho member khác và họ có thể import vào và dùng luôn trực tiếp được. <br>
Các bước để thực hiện export 1 file JSON chứa các request<br><br>
Bước 1.Tạo 1 collection: vào tab Collection trên Postman, sau đó click nút tạo mới 1 collection như hình vẽ<br><br>
   <img src="https://i.imgur.com/AsuN4Pi.png"> <br><br>
Tôi tạo 1 collection có tên Demo<br><br>
   <img src="https://i.imgur.com/bh2IDQf.png"> <br><br>
Bước 2.Bước tiếp theo là tạo và run 1 request, vào tab Hisroty, chọn option để Save request. Ở đây sau khi chọn Save request, ứng dụng sẽ cho phép người dùng chọn Collection muốn lưu request<br>
    <img src="https://i.imgur.com/Vz3jk8c.png"><br><br>
Ở đây ta Save request tại Collection Demo<br><br>
    <img src="https://i.imgur.com/pRG39AJ.png"><br><br>
Bước 3.Chúng ta đã có 1 set các request được chứa trong 1 Collection có tên Demo<br><br>
    <img src="https://i.imgur.com/aLt872o.png"><br><br>
Bước 4.Bước cuối cùng là Export ra để chia sẻ cho những người khác.<br><br>
   <img src="https://i.imgur.com/x2pQbE4.png"><br><br>
   <img src="https://i.imgur.com/PebXkan.png"><br><br>
- Chọn export bạn sẽ lấy được 1 file json, đó chính là Collection của bạn vừa thực hiện.<br>
<h3>Thực hiện import 1 file JSON chứa các request </h3>
Việc import vô cùng đơn giản. Trên thanh toolbar sẽ có 1 button là import, việc của bạn là ấn vào và trỏ đến file JSON vừa tạo.<br><br>
    <img src="https://i.imgur.com/wqAtc4v.png"><br><br>
    <img src="https://i.imgur.com/g98FSmm.png"><br><br>
Sau khi chọn xong bạn vào lại Collection và xem kết quả.<br>

# 2. Giới thiệu về Controller trong ASP.Net Core của Web API
- ASP.NET Core là mã nguồn mở mới và framework đa nền tảng (cross-platform) cho việc xây dựng những ứng dụng dựa trên kết nối đám mây, giống như web app cho mobile, chương trình client server giữa máy tính...bởi dữ liệu dạng json, xml.
- Controller là đối tượng xử lý các HTTP request được gởi lên bởi trình khách, nó không trả về các views(thành phần để hiển thị giao diện người dùng của ứng dụng (UI)) mà chúng chỉ trả về dữ liệu đơn thuần, dữ liệu còn lại sẽ được tự động chuyển sang dạng xml hoặc json tùy vào yêu cầu được chỉ tới.
- Các action HTTP (như GET, POST) tự động gắn kết vào các phương thức của controller (chính là các controller action) thông qua tên của chúng. Ví dụ

![startup_cs](https://user-images.githubusercontent.com/35052781/35293151-6ec47892-00a5-11e8-9cdd-957dc6304ac1.png)

Hoặc:
```
	[HttpPost]
        public async virtual Task<IActionResult> CreateEntityAsync([FromBody] TCreationDto creationDto)
        {
            if (!ModelState.IsValid) return BadRequest(new ApiError(ModelState));

            try
            {
                var ProductId = await _genericRepository.CreateAsync(creationDto);
                return Created("",new { id = ProductId });
            }
            catch (Exception ex)
            {
                return BadRequest(new ExceptionResponse(ex.Message));
            }
        }
```
- Thêm Controller:
  + Bước 1: Trong Solution Explorer, bấm chuột phải vào thư mục Controllers . Chọn Add > New Item . Trong hộp thoại Add New Item , chọn Web API Controller Class . Đặt tên cho lớp có dạng .Controller.
![new_controller](https://user-images.githubusercontent.com/35052781/35286103-a2249d52-0091-11e8-9736-ca5d7c6bf247.png)
  
  + Bước 2: Thay thế Class bằng mã code sau:
```
using System.Collections.Generic;
using Microsoft.AspNetCore.Mvc;
using TodoApi.Models;
using System.Linq;

namespace TodoApi.Controllers
{
    [Route("api/[controller]")]
    public class TodoController : Controller
    {
        private readonly TodoContext _context;

        public TodoController(TodoContext context)
        {
            _context = context;

            if (_context.TodoItems.Count() == 0)
            {
                _context.TodoItems.Add(new TodoItem { Name = "Item1" });
                _context.SaveChanges();
            }
        }       
    }
}
```
   + Bước 3: Thêm các phương thức GET, PUT, PUSH, DELETE,..vào controller vừa tạo và sử dụng nó.
   
# 3. Giới thiệu về file startup.cs trong ASP.Net Core của Web API
- File Startup.cs là một cách nâng cao để khởi động ứng dụng của bạn, và bây giờ là một phần không thể tách rời của ASP.NET Core
- File Startup.cs sẽ có dạng:
![startup](https://user-images.githubusercontent.com/35052781/35292232-77ac0bb2-00a2-11e8-80f8-06884fea2812.png)

- Lớp Startup có 2 phương thức đáng chú ý (ngoài constructor), là Configure() và ConfigureServices(), cả 2 phương thức này đều có thể sử dụng được một vài service có sẵn lúc khởi động, thông qua Dependency Injection(DI là một dịch vụ của Framework đảm bảo việc cung cấp các thành phần phụ thuộc khi cần thiết)
+ ConfigureServices(): thêm các dịch vụ vào container DI và có mã mặc định sẽ như sau:
```
// This method gets called by the runtime. Use this method to add services to the container.
public void ConfigureServices(IServiceCollection services)
{
    // Add framework services.
    services.AddMvc();
}
```
+ Configure(): cho phép chúng ta thêm middleware và dịch vụ vào đường ống HTTP.
```
public void Configure(IApplicationBuilder app, IHostingEnvironment env, ILoggerFactory loggerfactory)
{
    loggerFactory.AddConsole(Configuration.GetSection("Logging"));
    loggerFactory.AddDebug();

    if (env.IsDevelopment())
    {
        app.UseBrowserLink();
        app.UseDeveloperExceptionPage();
    }
    else
    {
        app.UseExceptionHandler("/Home/Error");
    }
    ...
}
```
  Lưu ý ba tham số:
  + IApplicationBuilder cho phép thêm các dịch vụ vào đường ống cho ứng dụng này.
  + IHostingEnvironment lưu trữ thông tin về môi trường lưu trữ hiện tại.
  + ILoggerFactory cho phép  thiết lập và thêm các nhà cung cấp đăng nhập.

# 4. Routing và các đặt tên route trong ASP.Net Core của Web API

- Web API Routing rất giống với MVC Routing. Sự khác biệt chính là Web API sử dụng phương pháp HTTP chứ không phải đường dẫn URI để chọn hành động.
- Routing Tables: 
  + Đối với mỗi thông điệp HTTP, ASP.NET Web API sẽ xác định controller nào sẽ nhận request bằng cách tham khảo bảng định tuyến (routing table)
  + Khi tạo một dự án Web API, dự án sẽ tạo ra một tuyến mặc định có dạng như sau:
   ```/api/{controller}/{id}```
  Trong đó {controller} chính là tên của Controller,  phương thức HTTP (GET / POST/ PUT /DELETE) chính là tên của phương thức của controller và {id} sẽ là giá trị gởi lên của tham số có tên là id.
  Ví dụ:
  
| HTTP Method | URI | Action|
|--------------|-------|------|
| GET |/api/products | GetAllProducts() | 2 x 3 |
| GET |	/api/products/5 | GetProduct(5) | 3 x 3 |
| POST |/api/products/ | HTTP Status 405 | 4 x 3 |
| GET |/api/users/ | HTTP Status 404 | 5 x 3 |<br>
<h3>6. Entity framework</h3><br>
Entity Framework là một bộ ánh xạ đối tượng – quan hệ cho phép người lập trình .NET  làm việc với dữ liệu quan hệ qua các đối tượng (object) nó giúp lập trình viên không cần viết mã cho (hầu hết) những gì liên quan đến truy cập dữ liệu. <br>
Kiến trúc của Entity Framework được minh họa như sau:<br><br>
  <img src="https://i.imgur.com/h94vJqK.png"><br><br>
Đây là các class tự động sinh ra tương ứng với mô hình dữ liệu. Các class này bao gồm:<br>
+ ObjectContext đại diện cho một database. ObjectContext có chức năng quản lý các kết nối, định nghĩa mô hình dữ liệu với metadata và thao tác với database. Lớp này cũng có thể thêm vào các phương thức đại diện cho các stored procedure trong database.<br>
+ ObjectSet<TEntity>là một  một tập hợp các entity. Mỗi đối tượng này tương ứng với một table. Có thể lấy được các đối tượng này thông qua các property tương ứng của ObjectContext.<br>
+ EntityObject, ComplexObject là các lớp tương ứng cho một dòng dữ liệu của table trong database. Khác biệt chính giữa hai loại này là ComplexObject không chứa primary key.<br>
+ EntityCollection<TEntity> và EntityReference<TEntity>: là các đối tượng thể hiện mối quan hệ (relationship) giữa hai entity class. Mỗi đối tượng này có thể được truy xuất thông qua các property của entity class.<br>
Để làm việc với Entity Framework một cách hoàn chỉnh chúng ta phải cài thêm Entity Framework bản mới nhất từ NuGet:<br>
B1. Tạo Project mới<br>
B2. Cài EF Power Tools vào Visual Studio: Tools -> Library Paskage Manager -> Manage NuGet Packages for Solution…<br><br>
   <img src="https://i.imgur.com/IMQB2he.png"><br><br>
Bến trái, chọn Online. Nhập Entity Framework Power Tools vào khung Search (góc trên, bên phải) chọn Entity Framework Power Tools -> Install. <br>
Khi đã cài được, bạn chuột phải trên tên Project sẽ thấy có menu Entity Framework.
<h3>5.Tạo database bằng code.</h3>
<h4>Khởi tạo Project</h4>
Tạo mới 1 project, chọn template là ASP.NET Core Web Application (.NET Core), đặt tên là TodoApi và chọn OK<br><br>
   <img src="https://i.imgur.com/XNAR1Cp.png"><br>
Trong hộp thoại mới ASP.NET Core Web Application - TodoApi , chọn mẫu Web API . Chọn OK<br><br>
   <img src="https://i.imgur.com/S3l9Zcy.png"><br><br>
<h4>Thêm model</h4>
Model là một object đại diện cho dữ liệu của bạn trong ứng dụng. Trong ví dụ này thì model duy nhất chỉ là một to-do item thôi.<br>
Chuột phải vào Project > Add > New Folder<br><br>
 <img src="https://i.imgur.com/NZ5UfsX.png"><br>
Tiếp tục chuột phải vào Folder Models > Add > Class, đặt tên class là TodoItem > Ok<br><br>
<img src="https://i.imgur.com/jKu1HYT.png"><br><br>
Thêm 3 Property vô<br>

```
   public string Key { get; set; }
   public string Name { get; set; }
   public bool IsComplete { get; set; }
```
<h4>Thêm Repository</h4>
Repository dùng để đóng gói data, và chứa logic cho việc truy cập dữ liệu và chuyển nó qua cho Entity Model.<br>
Để bắt đầu, chúng ta sẽ tạo một repository interface có tên ITodoRepository, dùng cách thêm class như trên, nhưng chọn template là Interface<br><br>
```
namespace todoapi.Models
{
    public interface ITodoRepository
    {
      void Add(TodoItem item);
      IEnumerable<TodoItem> GetAll();
       TodoItem Find(string key);
      TodoItem Remove(string key);
       void Update(TodoItem item);
    }
}
```
interface này định nghĩa các phương thức CRUD (Create – Read – Update – Delete)<br>
Tiếp theo, ta thêm class TodoRepository, triển khai các phương thức trong Interface mới tạo bên trên<br><br>
 ```
public class TodoRepository : ITodoRepository 
 { 
  private static ConcurrentDictionary<string, TodoItem> _todos = new ConcurrentDictionary<string, TodoItem>(); 
     public TodoRepository() 
     { 
         Add(new TodoItem { Name = "Item1" }); 
     } public void Add(TodoItem item) 
     { 
         item.Key = Guid.NewGuid().ToString(); 
         _todos[item.Key] = item; 
     } 
     public IEnumerable<TodoItem> GetAll() 
     { 
         return _todos.Values;
     } 
 
     public TodoItem Find(string key) 
     { 
         TodoItem item; 
         _todos.TryGetValue(key, out item); 
         return item; 
     } 
 
     public TodoItem Remove(string key) 
     { 
         TodoItem item; 
         _todos.TryGetValue(key, out item);
         _todos.TryRemove(key, out item);
         return item;
     } 
 
     public void Update(TodoItem item) 
     { 
         _todos[item.Key] = item; 
     } 
 }
 ```
<br><br>
Mở file Startup.cs, thêm dòng sau vô đầu<br>
 <h4>using todoapi.Models;</h4>
Trong phương thức configureServices, thêm đoạn code sau vô cuối<br>
 <h4> services.AddSingleton<ITodoRepository, TodoRepository>();</h4>
<h3>Thêm controller</h3>
Chuột phải lên thư mục Controller > Add > New Item<br>
Chọn Web API Controller Class, đặt tên TodoController<br><br>
<img src="https://i.imgur.com/ustRn46.png"><br><br>
Xóa hết code trong class đi, thay bằng đoạn code này.<br>
```
public class TodoController : Controller
{
    public ITodoRepository TodoItems { get; set; }
 
    public TodoController(ITodoRepository todoItems)
    {
        TodoItems = todoItems;
    }
}
```

Ta thử thêm các phương thức sau vào class TodoController<br><br>
```
[HttpGet]
public IEnumerable<TodoItem> GetAll()
{
    return _context.TodoItems.ToList();
}

[HttpGet("{id}", Name = "GetTodo")]
public IActionResult GetById(long id)
{
    var item = _context.TodoItems.FirstOrDefault(t => t.Id == id);
    if (item == null)
    {
        return NotFound();
    }
    return new ObjectResult(item);
}
```
<br><br>
Các phương pháp này thực hiện hai phương pháp GET:<br>
+ GET /api/todo<br>
+ GET /api/todo/{id}<br>
Dưới đây là ví dụ về phản hồi HTTP cho GetAllphương thức:<br><br>
```[
  {
    "id": 1,
    "name": "Item1",
    "isComplete": false
  }
]
```


