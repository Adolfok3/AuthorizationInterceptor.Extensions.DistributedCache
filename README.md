![AuthorizationInterceptor Icon](./resources/icon.png)

# AuthorizationInterceptor.Extensions.DistributedCache
[![GithubActions](https://github.com/Adolfok3/AuthorizationInterceptor.Extensions.DistributedCache/actions/workflows/main.yml/badge.svg)](https://github.com/Adolfok3/AuthorizationInterceptor.Extensions.DistributedCache/actions)
[![License](https://img.shields.io/badge/license-MIT-green)](./LICENSE)
[![Coverage Status](https://coveralls.io/repos/github/Adolfok3/AuthorizationInterceptor.Extensions.DistributedCache/badge.svg?branch=main)](https://coveralls.io/github/Adolfok3/AuthorizationInterceptor.Extensions.DistributedCache?branch=main)
[![NuGet Version](https://img.shields.io/nuget/vpre/AuthorizationInterceptor.Extensions.DistributedCache)](https://www.nuget.org/packages/AuthorizationInterceptor.Extensions.DistributedCache)

An interceptor for [AuthorizationInterceptor](https://github.com/Adolfok3/AuthorizationInterceptor) that uses a distributed cache abstraction to handle authorization headers. For more information on how to configure and use Authorization Interceptor, please check the main page of [AuthorizationInterceptor](https://github.com/Adolfok3/AuthorizationInterceptor).

### Installation
Run the following command in package manager console:
```
PM> Install-Package AuthorizationInterceptor.Extensions.DistributedCache
```

Or from the .NET CLI as:
```
dotnet add package AuthorizationInterceptor.Extensions.DistributedCache
```

### Setup
When adding Authorization Interceptor Handler, call the extension method `UseDistributedCacheInterceptor`:
```csharp
services.AddHttpClient("TargetApi")
        .AddAuthorizationInterceptorHandler<TargetApiAuthClass>(options =>
		{
			options.UseDistributedCacheInterceptor();
		})
```

> Note: Distributed cache is an abstraction that needs to be pre-configured using some libraries already available for .Net. Please check the official documentation of [Distributed caching in ASP.NET Core](https://learn.microsoft.com/en-us/aspnet/core/performance/caching/distributed)