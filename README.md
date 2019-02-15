# MACS3.Connected APIs

The following APIs are available:

* MACS3.Connected.SDK.Stability
* MACS3.Connected.SDK.Lashing
* MACS3.Connected.SDK.DangerousCargo

[Postman](postman.md)

The MACS3.Connected REST APIs enable developers to generate server stubs and client SDKs for e.g. JavaScript, Java, C#, Objective C, Swift, C++ and many more programming languages. To use a REST API, your application will make an HTTP request and parse the response. By default, the response format is JSON.
The technical documentation is based on the OpenAPI specification (formerly known as Swagger) and can be used by a variety of popular code-generators like [Swagger Codegen](https://swagger.io/tools/swagger-codegen) or [SwaggerHub](https://swagger.io/tools/swaggerhub).

Technical documentation is available at:

* https://api.stability.macs3.com
* https://api.lashing.macs3.com
* https://api.dago.macs3.com

## Sample: MACS3.Connected Stability Calculation with Microsoft Visual Studio and C# 7.1:

### Create a project
MACS3.Connected SDK packages can be installed into any .NET project, provided that the package supports the same target framework as the project.

### Add the MACS3.Connected Stability SDK from nuget.org
1. In Visual Studio select Tools > NuGet Package Manager > Package Manager Console menu command
2. Once the console opens, check that the Default project drop-down list shows the project into which you want to install the package.
3. Enter the command ```Install-Package MACS3.Connected.SDK.Stability```

### Get your API-KEY

### Use the SDK in your project:
```
using MACS3.Connected.SDK.Stability;
using Model = IO.Swagger.Model;

namespace MACS3.Connected.StabilityTest
{
    class Program
    {
        static async Task Main(string[] args)
        {
            var provider = new ApiKeyProvider { ApiKey = "YOUR-API-KEY" };
            
            using (var apiClient = await MACS3.Connected.SDK.Stability.API2.CreateClientAsync(provider))
            {
                try
                {
                    var parameter = new Model.CalculationsParameter();
                    var result = await apiClient.CalculateStabilityAsync(YOUR-IMO-NUMBER, parameter);
                }
                catch (ApiException)
                {
                }
            }
        }
    }
}
```

This is a dead simple stability-calculation sample. For more, please contact us or check out the technical documentation at https://api.stability.macs3.com

## Lashing calculation
This snippet explains how to perform a lashing calculation.

## DangerousCargo calculation
This snippet explains how to perform a dangerous-cargo calculation.
