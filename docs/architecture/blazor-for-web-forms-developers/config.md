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
# <a name="app-configuration"></a><span data-ttu-id="e1a86-103">应用配置</span><span class="sxs-lookup"><span data-stu-id="e1a86-103">App configuration</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="e1a86-104">在 Web 窗体中加载应用配置的主要方法是在服务器上使用*Web.config* &mdash;文件中的条目或*Web.config*引用的相关配置文件。可以使用静态`ConfigurationManager`对象与应用设置、数据存储库连接字符串以及添加到应用的其他扩展配置提供程序进行交互。</span><span class="sxs-lookup"><span data-stu-id="e1a86-104">The primary way to load app configuration in Web Forms is with entries in the *web.config* file&mdash;either on the server or a related configuration file referenced by *web.config*. You can use the static `ConfigurationManager` object to interact with app settings, data repository connection strings, and other extended configuration providers that are added into the app.</span></span> <span data-ttu-id="e1a86-105">通常可以看到与应用配置的交互，如以下代码所示：</span><span class="sxs-lookup"><span data-stu-id="e1a86-105">It's typical to see interactions with app configuration as seen in the following code:</span></span>

```csharp
var configurationValue = ConfigurationManager.AppSettings["ConfigurationSettingName"];
var connectionString = ConfigurationManager.ConnectionStrings["MyDatabaseConnectionName"].ConnectionString;
```

<span data-ttu-id="e1a86-106">对于ASP.NET核心和服务器端 Blazor，如果你的应用托管在 Windows IIS 服务器上，则*Web.config*文件可能会存在。</span><span class="sxs-lookup"><span data-stu-id="e1a86-106">With ASP.NET Core and server-side Blazor, the *web.config* file MAY be present if your app is hosted on a Windows IIS server.</span></span> <span data-ttu-id="e1a86-107">但是，没有`ConfigurationManager`使用此配置的交互，并且可以从其他源接收更结构化的应用配置。</span><span class="sxs-lookup"><span data-stu-id="e1a86-107">However, there's no `ConfigurationManager` interaction with this configuration, and you can receive more structured app configuration from other sources.</span></span> <span data-ttu-id="e1a86-108">让我们来看看如何收集配置以及如何仍然可以从*Web.config*文件访问配置信息。</span><span class="sxs-lookup"><span data-stu-id="e1a86-108">Let's take a look at how configuration is gathered and how you can still access configuration information from a *web.config* file.</span></span>

## <a name="configuration-sources"></a><span data-ttu-id="e1a86-109">配置源</span><span class="sxs-lookup"><span data-stu-id="e1a86-109">Configuration sources</span></span>

<span data-ttu-id="e1a86-110">ASP.NET Core 认识到许多配置源可能要用于你的应用。</span><span class="sxs-lookup"><span data-stu-id="e1a86-110">ASP.NET Core recognizes there are many configuration sources you may want to use for your app.</span></span> <span data-ttu-id="e1a86-111">默认情况下，框架尝试为您提供这些功能中的最佳功能。</span><span class="sxs-lookup"><span data-stu-id="e1a86-111">The framework attempts to offer you the best of these features by default.</span></span> <span data-ttu-id="e1a86-112">配置由ASP.NET核心从这些不同来源读取和聚合。</span><span class="sxs-lookup"><span data-stu-id="e1a86-112">Configuration is read and aggregated from these various sources by ASP.NET Core.</span></span> <span data-ttu-id="e1a86-113">以后为同一配置键加载的值优先于以前的值。</span><span class="sxs-lookup"><span data-stu-id="e1a86-113">Later loaded values for the same configuration key take precedence over earlier values.</span></span>

<span data-ttu-id="e1a86-114">ASP.NET Core 设计为具有云感知功能，并使操作员和开发人员更轻松地配置应用。</span><span class="sxs-lookup"><span data-stu-id="e1a86-114">ASP.NET Core was designed to be cloud-aware and to make configuration of apps easier for both operators and developers.</span></span> <span data-ttu-id="e1a86-115">ASP.NET核心是环境感知，知道它是否运行在你的`Production`或`Development`环境中。</span><span class="sxs-lookup"><span data-stu-id="e1a86-115">ASP.NET Core is environment-aware and knows if it's running in your `Production` or `Development` environment.</span></span> <span data-ttu-id="e1a86-116">环境指示器设置在系统环境变量`ASPNETCORE_ENVIRONMENT`中。</span><span class="sxs-lookup"><span data-stu-id="e1a86-116">The environment indicator is set in the `ASPNETCORE_ENVIRONMENT` system environment variable.</span></span> <span data-ttu-id="e1a86-117">如果未配置任何值，则应用默认在`Production`环境中运行。</span><span class="sxs-lookup"><span data-stu-id="e1a86-117">If no value is configured, the app defaults to running in the `Production` environment.</span></span>

<span data-ttu-id="e1a86-118">你的应用可以根据环境的名称触发和添加来自多个源的配置。</span><span class="sxs-lookup"><span data-stu-id="e1a86-118">Your app can trigger and add configuration from several sources based on the environment's name.</span></span> <span data-ttu-id="e1a86-119">默认情况下，配置按列出的顺序从以下资源加载：</span><span class="sxs-lookup"><span data-stu-id="e1a86-119">By default, configuration is loaded from the following resources in the order listed:</span></span>

1. <span data-ttu-id="e1a86-120">*应用程序设置.json*文件，如果存在</span><span class="sxs-lookup"><span data-stu-id="e1a86-120">*appsettings.json* file, if present</span></span>
1. <span data-ttu-id="e1a86-121">*应用设置。{ENVIRONMENT_NAME}.json*文件，如果存在</span><span class="sxs-lookup"><span data-stu-id="e1a86-121">*appsettings.{ENVIRONMENT_NAME}.json* file, if present</span></span>
1. <span data-ttu-id="e1a86-122">用户机密文件磁盘上，如果存在</span><span class="sxs-lookup"><span data-stu-id="e1a86-122">User secrets file on disk, if present</span></span>
1. <span data-ttu-id="e1a86-123">环境变量</span><span class="sxs-lookup"><span data-stu-id="e1a86-123">Environment variables</span></span>
1. <span data-ttu-id="e1a86-124">命令行参数</span><span class="sxs-lookup"><span data-stu-id="e1a86-124">Command-line arguments</span></span>

## <a name="appsettingsjson-format-and-access"></a><span data-ttu-id="e1a86-125">应用程序设置.json 格式和访问</span><span class="sxs-lookup"><span data-stu-id="e1a86-125">appsettings.json format and access</span></span>

<span data-ttu-id="e1a86-126">*appvalue.json*文件可以分层，其值结构如下 JSON：</span><span class="sxs-lookup"><span data-stu-id="e1a86-126">The *appsettings.json* file can be hierarchical with values structured like the following JSON:</span></span>

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

<span data-ttu-id="e1a86-127">当提供前面的 JSON 时，配置系统会平展子值并引用其完全限定的分层路径。</span><span class="sxs-lookup"><span data-stu-id="e1a86-127">When presented with the preceding JSON, the configuration system flattens child values and references their fully qualified hierarchical paths.</span></span> <span data-ttu-id="e1a86-128">冒号`:`（ ） 字符分隔层次结构中的每个属性。</span><span class="sxs-lookup"><span data-stu-id="e1a86-128">A colon (`:`) character separates each property in the hierarchy.</span></span> <span data-ttu-id="e1a86-129">例如，配置键`section1:key0`访问`section1`对象文本`key0`的值。</span><span class="sxs-lookup"><span data-stu-id="e1a86-129">For example, the configuration key `section1:key0` accesses the `section1` object literal's `key0` value.</span></span>

## <a name="user-secrets"></a><span data-ttu-id="e1a86-130">用户机密</span><span class="sxs-lookup"><span data-stu-id="e1a86-130">User secrets</span></span>

<span data-ttu-id="e1a86-131">用户机密包括：</span><span class="sxs-lookup"><span data-stu-id="e1a86-131">User secrets are:</span></span>

* <span data-ttu-id="e1a86-132">存储在开发人员工作站上的 JSON 文件中的配置值，在应用开发文件夹之外。</span><span class="sxs-lookup"><span data-stu-id="e1a86-132">Configuration values that are stored in a JSON file on the developer's workstation, outside of the app development folder.</span></span>
* <span data-ttu-id="e1a86-133">仅在`Development`环境中运行时加载。</span><span class="sxs-lookup"><span data-stu-id="e1a86-133">Only loaded when running in the `Development` environment.</span></span>
* <span data-ttu-id="e1a86-134">与特定应用关联。</span><span class="sxs-lookup"><span data-stu-id="e1a86-134">Associated with a specific app.</span></span>
* <span data-ttu-id="e1a86-135">使用 .NET 核心 CLI`user-secrets`的命令进行管理。</span><span class="sxs-lookup"><span data-stu-id="e1a86-135">Managed with the .NET Core CLI's `user-secrets` command.</span></span>

<span data-ttu-id="e1a86-136">通过执行`user-secrets`命令为机密存储配置应用：</span><span class="sxs-lookup"><span data-stu-id="e1a86-136">Configure your app for secrets storage by executing the `user-secrets` command:</span></span>

```dotnetcli
dotnet user-secrets init
```

<span data-ttu-id="e1a86-137">前面的命令向项目文件`UserSecretsId`添加一个元素。</span><span class="sxs-lookup"><span data-stu-id="e1a86-137">The preceding command adds a `UserSecretsId` element to the project file.</span></span> <span data-ttu-id="e1a86-138">该元素包含一个 GUID，用于将机密与应用相关联。</span><span class="sxs-lookup"><span data-stu-id="e1a86-138">The element contains a GUID, which is used to associate secrets with the app.</span></span> <span data-ttu-id="e1a86-139">然后，您可以使用 命令定义机密`set`。</span><span class="sxs-lookup"><span data-stu-id="e1a86-139">You can then define a secret with the `set` command.</span></span> <span data-ttu-id="e1a86-140">例如：</span><span class="sxs-lookup"><span data-stu-id="e1a86-140">For example:</span></span>

```dotnetcli
dotnet user-secrets set "Parent:ApiKey" "12345"
```

<span data-ttu-id="e1a86-141">前面的命令使`Parent:ApiKey`配置密钥在具有 值`12345`的开发人员工作站上可用。</span><span class="sxs-lookup"><span data-stu-id="e1a86-141">The preceding command makes the `Parent:ApiKey` configuration key available on a developer's workstation with the value `12345`.</span></span>

<span data-ttu-id="e1a86-142">有关创建、存储和管理用户机密的详细信息，请参阅[ASP.NET核心文档中开发中应用机密的安全存储](/aspnet/core/security/app-secrets)。</span><span class="sxs-lookup"><span data-stu-id="e1a86-142">For more information about creating, storing, and managing user secrets, see the [Safe storage of app secrets in development in ASP.NET Core](/aspnet/core/security/app-secrets) document.</span></span>

## <a name="environment-variables"></a><span data-ttu-id="e1a86-143">环境变量</span><span class="sxs-lookup"><span data-stu-id="e1a86-143">Environment variables</span></span>

<span data-ttu-id="e1a86-144">加载到应用配置中的下一组值是系统的环境变量。</span><span class="sxs-lookup"><span data-stu-id="e1a86-144">The next set of values loaded into your app configuration is the system's environment variables.</span></span> <span data-ttu-id="e1a86-145">现在，您可以通过配置 API 访问系统的所有环境变量设置。</span><span class="sxs-lookup"><span data-stu-id="e1a86-145">All of your system's environment variable settings are now accessible to you through the configuration API.</span></span> <span data-ttu-id="e1a86-146">在应用内读取时，分层值被拼平并由冒号字符分隔。</span><span class="sxs-lookup"><span data-stu-id="e1a86-146">Hierarchical values are flattened and separated by colon characters when read inside your app.</span></span> <span data-ttu-id="e1a86-147">但是，某些操作系统不允许冒号字符环境变量名称。</span><span class="sxs-lookup"><span data-stu-id="e1a86-147">However, some operating systems don't allow the colon character environment variable names.</span></span> <span data-ttu-id="e1a86-148">ASP.NET Core 通过在访问具有双下划线 （`__`） 的值时将值转换为冒号来解决此限制。</span><span class="sxs-lookup"><span data-stu-id="e1a86-148">ASP.NET Core addresses this limitation by converting values that have double-underscores (`__`) into a colon when they're accessed.</span></span> <span data-ttu-id="e1a86-149">上面`Parent:ApiKey`用户机密部分中的值可以使用环境变量`Parent__ApiKey`覆盖。</span><span class="sxs-lookup"><span data-stu-id="e1a86-149">The `Parent:ApiKey` value from the user secrets section above can be overridden with the environment variable `Parent__ApiKey`.</span></span>

## <a name="command-line-arguments"></a><span data-ttu-id="e1a86-150">命令行参数</span><span class="sxs-lookup"><span data-stu-id="e1a86-150">Command-line arguments</span></span>

<span data-ttu-id="e1a86-151">当应用启动时，也可以作为命令行参数提供配置。</span><span class="sxs-lookup"><span data-stu-id="e1a86-151">Configuration can also be provided as command-line arguments when your app is started.</span></span> <span data-ttu-id="e1a86-152">使用双虚线 （`--`） 或前斜`/`杠 （ ） 表示法来指示要设置的配置值的名称和要配置的值。</span><span class="sxs-lookup"><span data-stu-id="e1a86-152">Use the double-dash (`--`) or forward-slash (`/`) notation to indicate the name of the configuration value to set and the value to be configured.</span></span> <span data-ttu-id="e1a86-153">语法类似于以下命令：</span><span class="sxs-lookup"><span data-stu-id="e1a86-153">The syntax resembles the following commands:</span></span>

```dotnetcli
dotnet run CommandLineKey1=value1 --CommandLineKey2=value2 /CommandLineKey3=value3
dotnet run --CommandLineKey1 value1 /CommandLineKey2 value2
dotnet run Parent:ApiKey=67890
```

## <a name="the-return-of-webconfig"></a><span data-ttu-id="e1a86-154">Web.config 的回归</span><span class="sxs-lookup"><span data-stu-id="e1a86-154">The return of web.config</span></span>

<span data-ttu-id="e1a86-155">如果您将应用部署到 IIS 上的 Windows，则*Web.config*文件仍会配置 IIS 来管理你的应用。</span><span class="sxs-lookup"><span data-stu-id="e1a86-155">If you've deployed your app to Windows on IIS, the *web.config* file still configures IIS to manage your app.</span></span> <span data-ttu-id="e1a86-156">默认情况下，IIS 会添加对 ASP.NET核心模块 （ANCM） 的引用。</span><span class="sxs-lookup"><span data-stu-id="e1a86-156">By default, IIS adds a reference to the ASP.NET Core Module (ANCM).</span></span> <span data-ttu-id="e1a86-157">ANCM 是一个本机 IIS 模块，用于托管您的应用，以代替 Kestrel Web 服务器。</span><span class="sxs-lookup"><span data-stu-id="e1a86-157">ANCM is a native IIS module that hosts your app in place of the Kestrel web server.</span></span> <span data-ttu-id="e1a86-158">此*Web.config*部分类似于以下 XML 标记：</span><span class="sxs-lookup"><span data-stu-id="e1a86-158">This *web.config* section resembles the following XML markup:</span></span>

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

<span data-ttu-id="e1a86-159">可以通过嵌套`environmentVariables`元素中的元素来定义特定于应用的`aspNetCore`配置。</span><span class="sxs-lookup"><span data-stu-id="e1a86-159">App-specific configuration can be defined by nesting an `environmentVariables` element in the `aspNetCore` element.</span></span> <span data-ttu-id="e1a86-160">本节中定义的值作为环境变量呈现给ASP.NET核心应用。</span><span class="sxs-lookup"><span data-stu-id="e1a86-160">The values defined in this section are presented to the ASP.NET Core app as environment variables.</span></span> <span data-ttu-id="e1a86-161">环境变量在应用启动期间适当加载。</span><span class="sxs-lookup"><span data-stu-id="e1a86-161">The environment variables load appropriately during that segment of app startup.</span></span>

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

## <a name="read-configuration-in-the-app"></a><span data-ttu-id="e1a86-162">读取应用中的配置</span><span class="sxs-lookup"><span data-stu-id="e1a86-162">Read configuration in the app</span></span>

<span data-ttu-id="e1a86-163">ASP.NET核心通过<xref:Microsoft.Extensions.Configuration.IConfiguration>界面提供应用配置。</span><span class="sxs-lookup"><span data-stu-id="e1a86-163">ASP.NET Core provides app configuration through the <xref:Microsoft.Extensions.Configuration.IConfiguration> interface.</span></span> <span data-ttu-id="e1a86-164">此配置接口应由 Blazor 组件、Blazor 页面以及需要访问配置的任何其他ASP.NET Core 托管类请求。</span><span class="sxs-lookup"><span data-stu-id="e1a86-164">This configuration interface should be requested by your Blazor components, Blazor pages, and any other ASP.NET Core-managed class that needs access to configuration.</span></span> <span data-ttu-id="e1a86-165">ASP.NET核心框架将自动填充此接口，并配置了前面配置的已解决配置。</span><span class="sxs-lookup"><span data-stu-id="e1a86-165">The ASP.NET Core framework will automatically populate this interface with the resolved configuration configured earlier.</span></span> <span data-ttu-id="e1a86-166">在 Blazor 页或组件的 Razor 标记上，可以在`IConfiguration`*.razor*文件`@inject`顶部向对象注入指令，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e1a86-166">On a Blazor page or a component's Razor markup, you can inject the `IConfiguration` object with an `@inject` directive at the top of the *.razor* file like this:</span></span>

```razor
@inject IConfiguration Configuration
```

<span data-ttu-id="e1a86-167">在前面的语句使`IConfiguration`该对象作为`Configuration`变量在整个 Razor 模板的其余部分中可用。</span><span class="sxs-lookup"><span data-stu-id="e1a86-167">This preceding statement makes the `IConfiguration` object available as the `Configuration` variable throughout the rest of the Razor template.</span></span>

<span data-ttu-id="e1a86-168">可以通过指定作为索引器参数寻求的配置设置层次结构来读取各个配置设置：</span><span class="sxs-lookup"><span data-stu-id="e1a86-168">Individual configuration settings can be read by specifying the configuration setting hierarchy sought as an indexer parameter:</span></span>

```csharp
var mySetting = Configuration["section1:key0"];
```

<span data-ttu-id="e1a86-169">可以使用 方法<xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A>检索特定位置的密钥集合，其语法类似于`GetSection("section1")`从前面的示例中检索第 1 节的配置，从而获取整个配置部分。</span><span class="sxs-lookup"><span data-stu-id="e1a86-169">You can fetch entire configuration sections by using the <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> method to retrieve a collection of keys at a specific location with a syntax similar to `GetSection("section1")` to retrieve the configuration for section1 from the earlier example.</span></span>

## <a name="strongly-typed-configuration"></a><span data-ttu-id="e1a86-170">强类型配置</span><span class="sxs-lookup"><span data-stu-id="e1a86-170">Strongly typed configuration</span></span>

<span data-ttu-id="e1a86-171">使用 Web 窗体，可以创建从<xref:System.Configuration.ConfigurationSection>类型和相关类型继承的强类型配置类型。</span><span class="sxs-lookup"><span data-stu-id="e1a86-171">With Web Forms, it was possible to create a strongly typed configuration type that inherited from the <xref:System.Configuration.ConfigurationSection> type and associated types.</span></span> <span data-ttu-id="e1a86-172">A`ConfigurationSection`允许您为这些配置值配置某些业务规则和处理。</span><span class="sxs-lookup"><span data-stu-id="e1a86-172">A `ConfigurationSection` allowed you to configure some business rules and processing for those configuration values.</span></span>

<span data-ttu-id="e1a86-173">在ASP.NET Core 中，您可以指定将接收配置值的类层次结构。</span><span class="sxs-lookup"><span data-stu-id="e1a86-173">In ASP.NET Core, you can specify a class hierarchy that will receive the configuration values.</span></span> <span data-ttu-id="e1a86-174">这些类：</span><span class="sxs-lookup"><span data-stu-id="e1a86-174">These classes:</span></span>

* <span data-ttu-id="e1a86-175">不需要从父类继承。</span><span class="sxs-lookup"><span data-stu-id="e1a86-175">Don't need to inherit from a parent class.</span></span>
* <span data-ttu-id="e1a86-176">应包含`public`与要捕获的配置结构的属性匹配的属性和类型引用的属性。</span><span class="sxs-lookup"><span data-stu-id="e1a86-176">Should include `public` properties that match the properties and type references for the configuration structure you wish to capture.</span></span>

<span data-ttu-id="e1a86-177">对于前面的*appsettings.json*示例，您可以定义以下类来捕获这些值：</span><span class="sxs-lookup"><span data-stu-id="e1a86-177">For the earlier *appsettings.json* sample, you could define the following classes to capture the values:</span></span>

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

<span data-ttu-id="e1a86-178">可以通过将以下行添加到`Startup.ConfigureServices`方法来填充此类层次结构：</span><span class="sxs-lookup"><span data-stu-id="e1a86-178">This class hierarchy can be populated by adding the following line to the `Startup.ConfigureServices` method:</span></span>

```csharp
services.Configure<MyConfig>(Configuration);
```

<span data-ttu-id="e1a86-179">在应用的其余部分中，您可以将输入参数添加到类或类型`@inject``IOptions<MyConfig>`Razor 模板中的指令，以接收强类型配置设置。</span><span class="sxs-lookup"><span data-stu-id="e1a86-179">In the rest of the app, you can add an input parameter to classes or an `@inject` directive in Razor templates of type `IOptions<MyConfig>` to receive the strongly typed configuration settings.</span></span> <span data-ttu-id="e1a86-180">该`IOptions<MyConfig>.Value`属性将生成从`MyConfig`配置设置填充的值。</span><span class="sxs-lookup"><span data-stu-id="e1a86-180">The `IOptions<MyConfig>.Value` property will yield the `MyConfig` value populated from the configuration settings.</span></span>

```razor
@inject IOptions<MyConfig> options
@code {
    var MyConfiguration = options.Value;
    var theSetting = MyConfiguration.section1.key0;
}
```

<span data-ttu-id="e1a86-181">有关"选项"功能的详细信息，请参阅[ASP.NET核心文档中的选项模式](/aspnet/core/fundamentals/configuration/options#options-interfaces)。</span><span class="sxs-lookup"><span data-stu-id="e1a86-181">More information about the Options feature can be found in the [Options pattern in ASP.NET Core](/aspnet/core/fundamentals/configuration/options#options-interfaces) document.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e1a86-182">[上一页](middleware.md)
>[下一页](security-authentication-authorization.md)</span><span class="sxs-lookup"><span data-stu-id="e1a86-182">[Previous](middleware.md)
[Next](security-authentication-authorization.md)</span></span>
