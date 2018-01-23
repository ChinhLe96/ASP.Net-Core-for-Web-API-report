# ASP.Net-Core-for-Web-API-report
ASP.Net Core for Web API report

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

