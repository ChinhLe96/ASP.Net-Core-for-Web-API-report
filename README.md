
# 1.Cách sử dụng Postman: biến môi trường, biến sẵn có của postman, import, export. 
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
  
- Ví dụ: 
  + Phương thức GET:
```
        [HttpGet]
        public async Task<IActionResult> GetAll()
        {
            var products = await _context.Products.Include(p => p.ProductCategory).ToArrayAsync();
            return Ok(products);

        }
        [HttpGet("{id}")]
        public IActionResult GetById(Guid id)
        {
            var item = _context.Products.Include(p => p.ProductCategory).FirstOrDefault(t => t.Id == id);
            if (item == null)
            {
                return NotFound();
            }
            return new ObjectResult(item);
        }
```
  + Phương thức POST: 
``` 
        [HttpPost]
        public async Task<IActionResult> CreateProductAsync([FromBody] ProductForCreationDto productForCreationDto)
        {
            ProductEntity productEntity = new ProductEntity
            {
                Name = productForCreationDto.Name,
                ProductCategoryId = productForCreationDto.ProductCategoryId

            };
            try
            {
                await _context.Products.AddAsync(productEntity);

                await _context.SaveChangesAsync();

                return Created("", productEntity.Id);

            }
            catch (Exception ex)
            {
                return BadRequest(ex.Message);
            }

        }
```
   + Phương thức PUT:
```
        [HttpPut("{id}")]
        public IActionResult Update(Guid id, [FromBody] ProductEntity item)
        {
            if (item == null || item.Id != id)
            {
                return BadRequest();
            }

            var pro = _context.Products.Include(p => p.ProductCategory).FirstOrDefault(t => t.Id == id);
            if (pro == null)
            {
                return NotFound();
            }

            pro.Name = item.Name;
            //pro.ProductCategoryId = item.ProductCategoryId;
            //pro.ProductCategory = item.ProductCategory;

            _context.Products.Update(pro);
            _context.SaveChanges();
            return new NoContentResult();
        }
```
  + Phương thức DELETE:
```
        [HttpDelete("{id}")]
        public IActionResult Delete(Guid id)
        {
            try
            {
                var todo = _context.Products.FirstOrDefault(t => t.Id == id);
                if (todo == null)
                {
                    return NotFound();
                }

                _context.Products.Remove(todo);
                _context.SaveChanges();
                return new NoContentResult();
            }catch(Exception ex)
            {
                return BadRequest(ex.Message);
            }
        }
```
   
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

# 5.Tạo database bằng code
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
Thêm 3 Property vô

```
   public string Key { get; set; }
   public string Name { get; set; }
   public bool IsComplete { get; set; }
```
<br>

# 6. Entity framework <br>

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

# 7 Auto Mapping
- Auto Mapper là gì ?
<br>
Automapper là 1 thư viện mapping object-object. Nó cho phép copy giá trị từ 2 object có các property (thuộc tính) giống tên nhau - không phân biệt hoa thường. Hơn thế nữa, nó còn có thể map các property giống tên nhưng khác kiểu dữ liệu(*) và cho phép bạn custom việc chuyển đổi giữa các property theo ý mình.
<br>
- Vì sao phải sử dụng AutoMapper:
<br>
<img src="https://i.imgur.com/NTBrnIy.png">
<br>
hoặc đại loại 1 đoạn code copy giá trị tương tự:
<img src="https://i.imgur.com/nj3bxBv.png">
<br>
Automapper cho phép download miễn phí thông qua nuget, bạn có thể sử dụng lệnh sau trong Package Manager Console để cài đặt version mới nhất: **Install-Package AutoMapper** <br>
- Cách sử dụng AutoMapper:<br>
Giả sử bạn có 2 class <br>
<img src="https://i.imgur.com/skMaAjV.png"><br>
Và đây là mã trong phương pháp ConfigureServices.<br>
<img src="https://i.imgur.com/ka89DIq.png"><br>
Bạn có thể ánh xạ các lớp bằng cách sử dụng phương pháp Map của đối tượng Mapper. Để sử dụng đối tượng Mapper trong bộ điều khiển, bạn có thể chèn nó bằng cách sử dụng sự phụ thuộc của ASP.NET Core.<br>
<img src="https://i.imgur.com/69B6Tg7.png"><br>
Đây là ảnh chụp màn hình của bản đồ sử dụng Automapper.<br>
<img src="https://i.imgur.com/doYJD46.png"><br>
Đây là việc triển khai lớp hồ sơ, tương tự như thực hiện hiện tại ngoại trừ tất cả các ánh xạ sẽ nằm trong lớp này.<br>
<img src="https://i.imgur.com/lYolPCX.png"><br>
Và bạn có thể sử dụng nó như thế này trong lớp Startup.<br>
<img src="https://i.imgur.com/kamaYyz.png"><br>

# 8 Vai trò của Controller, Repository, Entity, Model
- Mô hình MVC là mô hình kiến trúc phần mềm với 3 thành phần Models, Views, và Controller. Khi sử dụng mô hình này, yêu cầu người dùng sẽ được chuyển đến (routed) một Controller, Controller này có trách nhiệm làm việc với Model để thực hiện các hành động của người dùng và có thể lấy kết quả của các câu truy vấn. Controller sẽ chọn View tương ứng để hiển thị cho người dùng, và cung cấp cho cho nó với bất kỳ dữ liệu của Model mà nó đòi hỏi. 
<br>
<img src="https://i.imgur.com/bT59Cre.png"><br>
- Chức năng của Model<br>
Chứa tất cả các nghiệp vụ logic, các phương thức xử lý, truy xuất database, những đối tượng mô tả dữ liệu như Class, hàm xử lý
<br>
- Chức năng của Controller<br>
Controller là thành phần xử lý tương tác người dùng, làm việc với các Model, và cuối cùng là chọn một View để hiển thị. Trong một ứng dụng MVC, View chỉ để hiển thị thông tin, Controller xử lý và phản ứng và tương tác với người dùng. Trong mô hình MVC, Controller là điểm khởi đầu, có trách nhiệm lựa chọn các Model để làm việc và View để hiển thị
<br>
### Entity framework
Entity Framework hỗ trợ 3 cách làm việc với cơ sở dữ liệu Database First, Model First, Code First, cụ thể theo 4 workflow như sau:

- Database First: Trong trường hợp bạn muốn làm việc với database đã có sẵn. Sử dụng công cụ thiết kế có sẵn trong Visual Studio kết nối database sẽ giúp ta tạo ra các model bao gồm lớp và thuộc tính . Các thông tin về cấu trúc dữ liệu của bạn (Store Schema), mô hình dữ liệu (Conceptual Model), và mối quan hệ giữa chúng được lưu trữ dưới dạng XML trong một tập tin .edmx. Entity Framework cung cấp một giao diện hiển thị và chỉnh sửa các tập tin .edmx.
- Model First: Trong trường hợp này, chúng ta sử dụng các thiết kế Entity Framework trong Visual Studio tạo ra model trong một tập tin .edmx. Dùng công cụ để generated code từ bản thiết kế model ra database.
- Code First: Riêng với cách này có 2 lựa chọn, làm việc với database có sẵn hoặc sẽ tạo mới. Nhưng dù làm với cách nào, chúng ta cũng dùng codebehind để xử lý là chính. Không dùng các tool, giao diện trực quan giống như 2 cách bên trên.
Việc lựa chọn workflow  phù hợp cho chương trình của bạn phụ thuộc vào câu trả lời cho hai câu hỏi sau:
Câu hỏi 1: Bạn tạo sẵn cơ sở dữ liệu với các bảng hay chưa?
Câu hỏi 2: Bạn muốn tạo các Model theo cách viết code hay dựa vào giao diện thiết kế?
Trong quy trình xây dựng ứng dụng, thông thường cơ sở dữ liệu sẽ được xây dựng trước việc này có thể do nhân viên phân tích thiết kế chuyên về cơ sở dữ liệu làm hay với các ứng dụng đơn giản hơn thì lập trình viên thực hiện. Sau đó tùy theo yêu cầu phát sinh trong quá trình thực hiện hay từ khách hàng mà ta điều chỉnh cơ sở dữ liệu này. Vậu câu trả lời cho  câu hỏi 1 thông thường là có.
Câu trả lời cho câu hỏi  hai thì tùy vào lập trình vên với các ứng dụng đơn giản nhanh thì có thể thiết kế model theo giao diện, nếu lập trình viên cần kiểm soát chặt chẽ code của chương trình thì việc code model bằng tay được thược hiện.

### Repository
- đơn giản là một lớp trung gian giữa tầng business và tầng truy xuất dữ liệu. Nếu bạn sử dụng Entity Framework trong ASP.NET Core MVC hay trong ASP.NET MVC thì business là tầng xử lý nghiệp vụ của dự án, còn Data chính là tầng dùng để chứa các lớp DbContext và các class entity. Ở trong ASP.NET thì repository sẽ được sử dụng để nhằm điều chỉnh dữ liệu trước khi dữ liệu được truyền lên business logic hoặc truyền xuống tầng data


