```sh
> 0xFF
```

```csharp
[Route("api/[controller]")]
public class UserController : BaseController
{
    [HttpGet("{id}")]
    public async Task<UserDTO> GetById(Guid id) 
    {
        var user = await _memoryBus.Get(new GetUserById(id));
        return Ok(user)
    }   
}
```
