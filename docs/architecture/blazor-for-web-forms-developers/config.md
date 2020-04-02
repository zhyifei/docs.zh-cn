---
title: 应用配置
description: 了解如何配置 Blazor 应用而不使用配置管理器。
author: csharpfritz
ms.author: jefritz
ms.date: 04/01/2020
ms.openlocfilehash: c780a395f72e2520af86c20c7f6618953a528ff7
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588251"
---
# <a name="app-configuration"></a>应用配置

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

在 Web 窗体中加载应用配置的主要方法是在服务器上使用*Web.config* &mdash;文件中的条目或*Web.config*引用的相关配置文件。可以使用静态`ConfigurationManager`对象与应用设置、数据存储库连接字符串以及添加到应用的其他扩展配置提供程序进行交互。 通常可以看到与应用配置的交互，如以下代码所示：

```csharp
var configurationValue = ConfigurationManager.AppSettings["ConfigurationSettingName"];
var connectionString = ConfigurationManager.ConnectionStrings["MyDatabaseConnectionName"].ConnectionString;
```

对于ASP.NET核心和服务器端 Blazor，如果你的应用托管在 Windows IIS 服务器上，则*Web.config*文件可能会存在。 但是，没有`ConfigurationManager`使用此配置的交互，并且可以从其他源接收更结构化的应用配置。 让我们来看看如何收集配置以及如何仍然可以从*Web.config*文件访问配置信息。

## <a name="configuration-sources"></a>配置源

ASP.NET Core 认识到许多配置源可能要用于你的应用。 默认情况下，框架尝试为您提供这些功能中的最佳功能。 配置由ASP.NET核心从这些不同来源读取和聚合。 以后为同一配置键加载的值优先于以前的值。

ASP.NET Core 设计为具有云感知功能，并使操作员和开发人员更轻松地配置应用。 ASP.NET核心是环境感知，知道它是否运行在你的`Production`或`Development`环境中。 环境指示器设置在系统环境变量`ASPNETCORE_ENVIRONMENT`中。 如果未配置任何值，则应用默认在`Production`环境中运行。

你的应用可以根据环境的名称触发和添加来自多个源的配置。 默认情况下，配置按列出的顺序从以下资源加载：

1. *应用程序设置.json*文件，如果存在
1. *应用设置。{ENVIRONMENT_NAME}.json*文件，如果存在
1. 用户机密文件磁盘上，如果存在
1. 环境变量
1. 命令行参数

## <a name="appsettingsjson-format-and-access"></a>应用程序设置.json 格式和访问

*appvalue.json*文件可以分层，其值结构如下 JSON：

```json
{
  "section0": {
    "key0": "value",
    "key1": "value"
  },
  "section1": {
    "key0": "value",
    "key1": "value"
  }
}
```

当提供前面的 JSON 时，配置系统会平展子值并引用其完全限定的分层路径。 冒号`:`（ ） 字符分隔层次结构中的每个属性。 例如，配置键`section1:key0`访问`section1`对象文本`key0`的值。

## <a name="user-secrets"></a>用户机密

用户机密包括：

* 存储在开发人员工作站上的 JSON 文件中的配置值，在应用开发文件夹之外。
* 仅在`Development`环境中运行时加载。
* 与特定应用关联。
* 使用 .NET 核心 CLI`user-secrets`的命令进行管理。

通过执行`user-secrets`命令为机密存储配置应用：

```dotnetcli
dotnet user-secrets init
```

前面的命令向项目文件`UserSecretsId`添加一个元素。 该元素包含一个 GUID，用于将机密与应用相关联。 然后，您可以使用 命令定义机密`set`。 例如：

```dotnetcli
dotnet user-secrets set "Parent:ApiKey" "12345"
```

前面的命令使`Parent:ApiKey`配置密钥在具有 值`12345`的开发人员工作站上可用。

有关创建、存储和管理用户机密的详细信息，请参阅[ASP.NET核心文档中开发中应用机密的安全存储](/aspnet/core/security/app-secrets)。

## <a name="environment-variables"></a>环境变量

加载到应用配置中的下一组值是系统的环境变量。 现在，您可以通过配置 API 访问系统的所有环境变量设置。 在应用内读取时，分层值被拼平并由冒号字符分隔。 但是，某些操作系统不允许冒号字符环境变量名称。 ASP.NET Core 通过在访问具有双下划线 （`__`） 的值时将值转换为冒号来解决此限制。 上面`Parent:ApiKey`用户机密部分中的值可以使用环境变量`Parent__ApiKey`覆盖。

## <a name="command-line-arguments"></a>命令行参数

当应用启动时，也可以作为命令行参数提供配置。 使用双虚线 （`--`） 或前斜`/`杠 （ ） 表示法来指示要设置的配置值的名称和要配置的值。 语法类似于以下命令：

```dotnetcli
dotnet run CommandLineKey1=value1 --CommandLineKey2=value2 /CommandLineKey3=value3
dotnet run --CommandLineKey1 value1 /CommandLineKey2 value2
dotnet run Parent:ApiKey=67890
```

## <a name="the-return-of-webconfig"></a>Web.config 的回归

如果您将应用部署到 IIS 上的 Windows，则*Web.config*文件仍会配置 IIS 来管理你的应用。 默认情况下，IIS 会添加对 ASP.NET核心模块 （ANCM） 的引用。 ANCM 是一个本机 IIS 模块，用于托管您的应用，以代替 Kestrel Web 服务器。 此*Web.config*部分类似于以下 XML 标记：

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <location path="." inheritInChildApplications="false">
    <system.webServer>
      <handlers>
        <add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModuleV2" resourceType="Unspecified" />
      </handlers>
      <aspNetCore processPath=".\MyApp.exe"
                  stdoutLogEnabled="false"
                  stdoutLogFile=".\logs\stdout"
                  hostingModel="inprocess" />
    </system.webServer>
  </location>
</configuration>
```

可以通过嵌套`environmentVariables`元素中的元素来定义特定于应用的`aspNetCore`配置。 本节中定义的值作为环境变量呈现给ASP.NET核心应用。 环境变量在应用启动期间适当加载。

```xml
<aspNetCore processPath="dotnet"
      arguments=".\MyApp.dll"
      stdoutLogEnabled="false"
      stdoutLogFile=".\logs\stdout"
      hostingModel="inprocess">
  <environmentVariables>
    <environmentVariable name="ASPNETCORE_ENVIRONMENT" value="Development" />
    <environmentVariable name="Parent:ApiKey" value="67890" />
  </environmentVariables>
</aspNetCore>
```

## <a name="read-configuration-in-the-app"></a>读取应用中的配置

ASP.NET核心通过<xref:Microsoft.Extensions.Configuration.IConfiguration>界面提供应用配置。 此配置接口应由 Blazor 组件、Blazor 页面以及需要访问配置的任何其他ASP.NET Core 托管类请求。 ASP.NET核心框架将自动填充此接口，并配置了前面配置的已解决配置。 在 Blazor 页或组件的 Razor 标记上，可以在`IConfiguration`*.razor*文件`@inject`顶部向对象注入指令，如下所示：

```razor
@inject IConfiguration Configuration
```

在前面的语句使`IConfiguration`该对象作为`Configuration`变量在整个 Razor 模板的其余部分中可用。

可以通过指定作为索引器参数寻求的配置设置层次结构来读取各个配置设置：

```csharp
var mySetting = Configuration["section1:key0"];
```

可以使用 方法<xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A>检索特定位置的密钥集合，其语法类似于`GetSection("section1")`从前面的示例中检索第 1 节的配置，从而获取整个配置部分。

## <a name="strongly-typed-configuration"></a>强类型配置

使用 Web 窗体，可以创建从<xref:System.Configuration.ConfigurationSection>类型和相关类型继承的强类型配置类型。 A`ConfigurationSection`允许您为这些配置值配置某些业务规则和处理。

在ASP.NET Core 中，您可以指定将接收配置值的类层次结构。 这些类：

* 不需要从父类继承。
* 应包含`public`与要捕获的配置结构的属性匹配的属性和类型引用的属性。

对于前面的*appsettings.json*示例，您可以定义以下类来捕获这些值：

```csharp
public class MyConfig
{
    public MyConfigSection section0 { get; set;}

    public MyConfigSection section1 { get; set;}
}

public class MyConfigSection
{
    public string key0 { get; set; }

    public string key1 { get; set; }
}
```

可以通过将以下行添加到`Startup.ConfigureServices`方法来填充此类层次结构：

```csharp
services.Configure<MyConfig>(Configuration);
```

在应用的其余部分中，您可以将输入参数添加到类或类型`@inject``IOptions<MyConfig>`Razor 模板中的指令，以接收强类型配置设置。 该`IOptions<MyConfig>.Value`属性将生成从`MyConfig`配置设置填充的值。

```razor
@inject IOptions<MyConfig> options
@code {
    var MyConfiguration = options.Value;
    var theSetting = MyConfiguration.section1.key0;
}
```

有关"选项"功能的详细信息，请参阅[ASP.NET核心文档中的选项模式](/aspnet/core/fundamentals/configuration/options#options-interfaces)。

>[!div class="step-by-step"]
>[上一页](middleware.md)
>[下一页](security-authentication-authorization.md)
