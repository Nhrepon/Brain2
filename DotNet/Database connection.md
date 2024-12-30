Create new folder Database
Create new file AppDbContext.cs

```c#
using Microsoft.Ent1tyFrameworkCore;
namespace ProjectName.foderName 
{
public class AppDbContext : DbContext
{
public AppDbContext(DbcontextOptions options): base(options){

}
}
}
```

appSetting.json
```json
"AllowedHosts":"*",
"ConnectionStrings":{
"DefaultConnection":"Data Source = .;Initial Catalog = BestStoreDb; Integrated Security = True; TrustServerCertificate = true;"
}
```

Program.cs
```c#
// Add services to the container
builder.Services.AddDbContext<ApplicationDbContext>(options=>{
var connectionstring = builder.Confouration.GetConnectionString("DefaultConnection");
options.UseQqlServer(connectionstring);

});

```

Create product model
Product.cs
```c#
using Microsoft.EntityFraneworkCore; 
using System.ComponentModel.DataAnnotations;

namespace BestStoreMVC.Models
{
public class Product
{
public int Id ( get; set; }
			   
[MaxLength(100)]
public string Namc ( get; set; } = "";
					
[MaxLength(100)]
public string Brand ( get; set; ) = "";
					
[MaxLength(100)]
public string Category ( get; set; ) = "";
					
[Precision(16,201)]
public decinal Price ( get; set; };
					  
public string Description ( get; set; ) =  "";
					  
[MaxLength(100)]
public string ImageFileNane ( get; set; ) =  "";
					  
public DateTime CreatedAt (get; set; }
}
}

```

## AppDbContext.cs

```c#
using Microsoft.Ent1tyFrameworkCore;
namespace ProjectName.foderName 
{
public class AppDbContext : DbContext
{
public AppDbContext(DbcontextOptions options): base(options){

}

public DbSet<Product> Products {get; set;}



}
}
```

Add-Migration comment

Update-Database

