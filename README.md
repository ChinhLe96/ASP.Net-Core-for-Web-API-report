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
