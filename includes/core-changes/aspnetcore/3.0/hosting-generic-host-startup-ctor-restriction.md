---
ms.openlocfilehash: d1ddba72ce25c5e01025d916d52f785b5a1a9e71
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901887"
---
### <a name="hosting-generic-host-restricts-startup-constructor-injection"></a><span data-ttu-id="8d16f-101">托管：通用主机限制 Startup 构造函数注入</span><span class="sxs-lookup"><span data-stu-id="8d16f-101">Hosting: Generic host restricts Startup constructor injection</span></span>

<span data-ttu-id="8d16f-102">通用主机支持的 `Startup` 类构造函数注入的唯一类型为 `IHostEnvironment`、`IWebHostEnvironment` 和 `IConfiguration`。</span><span class="sxs-lookup"><span data-stu-id="8d16f-102">The only types the generic host supports for `Startup` class constructor injection are `IHostEnvironment`, `IWebHostEnvironment`, and `IConfiguration`.</span></span> <span data-ttu-id="8d16f-103">使用 `WebHost` 的应用不受影响。</span><span class="sxs-lookup"><span data-stu-id="8d16f-103">Apps using `WebHost` are unaffected.</span></span>

#### <a name="change-description"></a><span data-ttu-id="8d16f-104">更改描述</span><span class="sxs-lookup"><span data-stu-id="8d16f-104">Change description</span></span>

<span data-ttu-id="8d16f-105">在低于 ASP.NET Core 3.0 的版本中，构造函数注入可用于 `Startup` 类的构造函数中的任意类型。</span><span class="sxs-lookup"><span data-stu-id="8d16f-105">Prior to ASP.NET Core 3.0, constructor injection could be used for arbitrary types in the `Startup` class's constructor.</span></span> <span data-ttu-id="8d16f-106">在 ASP.NET Core 3.0 中，Web 堆栈将重新平台化到通用主机库上。</span><span class="sxs-lookup"><span data-stu-id="8d16f-106">In ASP.NET Core 3.0, the web stack was replatformed onto the generic host library.</span></span> <span data-ttu-id="8d16f-107">可以在模板的 Program .cs  文件中查看更改：</span><span class="sxs-lookup"><span data-stu-id="8d16f-107">You can see the change in the *Program.cs* file of the templates:</span></span>

<span data-ttu-id="8d16f-108">**ASP.NET Core 2.x：**</span><span class="sxs-lookup"><span data-stu-id="8d16f-108">**ASP.NET Core 2.x:**</span></span>

<https://github.com/dotnet/aspnetcore/blob/5cb615fcbe8559e49042e93394008077e30454c0/src/Templating/src/Microsoft.DotNet.Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L20-L22>

<span data-ttu-id="8d16f-109">**ASP.NET Core 3.0：**</span><span class="sxs-lookup"><span data-stu-id="8d16f-109">**ASP.NET Core 3.0:**</span></span>

<https://github.com/dotnet/aspnetcore/blob/b1ca2c1155da3920f0df5108b9fedbe82efaa11c/src/ProjectTemplates/Web.ProjectTemplates/content/EmptyWeb-CSharp/Program.cs#L19-L24>

<span data-ttu-id="8d16f-110">`Host` 使用一个依赖关系注入 (DI) 容器生成应用。</span><span class="sxs-lookup"><span data-stu-id="8d16f-110">`Host` uses one dependency injection (DI) container to build the app.</span></span> <span data-ttu-id="8d16f-111">`WebHost` 使用两个容器：一个用于主机，另一个用于应用。</span><span class="sxs-lookup"><span data-stu-id="8d16f-111">`WebHost` uses two containers: one for the host and one for the app.</span></span> <span data-ttu-id="8d16f-112">因此，`Startup` 构造函数不再支持自定义服务注入。</span><span class="sxs-lookup"><span data-stu-id="8d16f-112">As a result, the `Startup` constructor no longer supports custom service injection.</span></span> <span data-ttu-id="8d16f-113">只能注入 `IHostEnvironment`、`IWebHostEnvironment` 和 `IConfiguration`。</span><span class="sxs-lookup"><span data-stu-id="8d16f-113">Only `IHostEnvironment`, `IWebHostEnvironment`, and `IConfiguration` can be injected.</span></span> <span data-ttu-id="8d16f-114">此更改可防止出现 DI 问题，例如重复创建单一实例服务。</span><span class="sxs-lookup"><span data-stu-id="8d16f-114">This change prevents DI issues such as the duplicate creation of a singleton service.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="8d16f-115">引入的版本</span><span class="sxs-lookup"><span data-stu-id="8d16f-115">Version introduced</span></span>

<span data-ttu-id="8d16f-116">3.0</span><span class="sxs-lookup"><span data-stu-id="8d16f-116">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="8d16f-117">更改原因</span><span class="sxs-lookup"><span data-stu-id="8d16f-117">Reason for change</span></span>

<span data-ttu-id="8d16f-118">此更改是将 Web 堆栈重新平台化到通用主机库的结果。</span><span class="sxs-lookup"><span data-stu-id="8d16f-118">This change is a consequence of replatforming the web stack onto the generic host library.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="8d16f-119">建议操作</span><span class="sxs-lookup"><span data-stu-id="8d16f-119">Recommended action</span></span>

<span data-ttu-id="8d16f-120">将服务注入 `Startup.Configure` 方法签名。</span><span class="sxs-lookup"><span data-stu-id="8d16f-120">Inject services into the `Startup.Configure` method signature.</span></span> <span data-ttu-id="8d16f-121">例如：</span><span class="sxs-lookup"><span data-stu-id="8d16f-121">For example:</span></span>

```csharp
public void Configure(IApplicationBuilder app, IOptions<MyOptions> options)
```

#### <a name="category"></a><span data-ttu-id="8d16f-122">类别</span><span class="sxs-lookup"><span data-stu-id="8d16f-122">Category</span></span>

<span data-ttu-id="8d16f-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="8d16f-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="8d16f-124">受影响的 API</span><span class="sxs-lookup"><span data-stu-id="8d16f-124">Affected APIs</span></span>

<span data-ttu-id="8d16f-125">None</span><span class="sxs-lookup"><span data-stu-id="8d16f-125">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
