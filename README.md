Hello-World
===========

## APIエラー時の戻り値
ProblemDetails
ValidationProblemDetails 

### モデルValidation失敗時の挙動を変更するには
```
services.Configure<ApiBehaviorOptions>(o =>
{
    o.InvalidModelStateResponseFactory = actionContext =>
        new BadRequestObjectResult(actionContext.ModelState);
});
```

### .NET Coreの互換性
```
public void ConfigureServices(IServiceCollection services)
{
    services.AddMvc()
        .SetCompatibilityVersion(CompatibilityVersion.Version_2_2);
}
```