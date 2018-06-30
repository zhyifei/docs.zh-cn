---
title: 将旧版整体式 .NET Framework 应用程序迁移到 Windows 容器
description: 容器化 .NET 应用程序的 .NET 微服务体系结构 | 将旧版整体式 .NET Framework 应用程序迁移到 Windows 容器
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 01b84d29a559bde02ebd30535488c272d5208167
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2018
ms.locfileid: "37106510"
---
# <a name="migrating-legacy-monolithic-net-framework-applications-to-windows-containers"></a><span data-ttu-id="18325-103">将旧版整体式 .NET Framework 应用程序迁移到 Windows 容器</span><span class="sxs-lookup"><span data-stu-id="18325-103">Migrating Legacy Monolithic .NET Framework Applications to Windows Containers</span></span>

<span data-ttu-id="18325-104">Windows 容器可作为一种用于改善开发和测试环境以及部署基于旧版 .NET Framework 技术（如 Web 窗体）的应用程序的途径。以这种方式将容器用于旧版应用程序称为“直接迁移”方案。</span><span class="sxs-lookup"><span data-stu-id="18325-104">*Windows Containers can be used as a way to improve development and test environments, and to deploy applications that are based on legacy .NET Framework technologies like Web* *Forms. Using containers for legacy applications in this way is referred to as a “lift and shift” scenario.*</span></span>

<span data-ttu-id="18325-105">本指南前面几节倡导了微服务体系结构，即业务应用程序分布在不同的容器中，每个应用程序运行一个小型的集中式服务。</span><span class="sxs-lookup"><span data-stu-id="18325-105">Earlier sections of this guide have championed a microservices architecture where business applications are distributed among different containers, each running a small, focused service.</span></span> <span data-ttu-id="18325-106">该目标具有诸多优点。</span><span class="sxs-lookup"><span data-stu-id="18325-106">That goal has many benefits.</span></span> <span data-ttu-id="18325-107">在新的开发中，强烈建议采用这种方法。</span><span class="sxs-lookup"><span data-stu-id="18325-107">In new development, that approach is strongly recommended.</span></span> <span data-ttu-id="18325-108">企业关键型应用程序还非常利于证明体系结构重建和重新实现的成本。</span><span class="sxs-lookup"><span data-stu-id="18325-108">Enterprise-critical applications will also benefit enough to justify the cost of a rearchitecture and reimplementation.</span></span>

<span data-ttu-id="18325-109">但并不是每个应用程序都非常利于证明成本。</span><span class="sxs-lookup"><span data-stu-id="18325-109">But not every application will benefit enough to justify the cost.</span></span> <span data-ttu-id="18325-110">这并不表示这些应用程序不能用于容器方案中。</span><span class="sxs-lookup"><span data-stu-id="18325-110">That does not mean that those applications cannot be used in container scenarios.</span></span>

<span data-ttu-id="18325-111">本节会探讨 eShopOnContainers 的应用程序，如图 7-1 所示。</span><span class="sxs-lookup"><span data-stu-id="18325-111">In this section, we will explore an application for eShopOnContainers, shown in Figure 7-1.</span></span> <span data-ttu-id="18325-112">eShopOnContainers 企业团队的成员会将此应用程序用于查看和编辑产品目录。</span><span class="sxs-lookup"><span data-stu-id="18325-112">This application would be used by members of the eShopOnContainers enterprise team to view and edit the product catalog.</span></span>

![](./media/image1.png)

<span data-ttu-id="18325-113">图 7-1。</span><span class="sxs-lookup"><span data-stu-id="18325-113">**Figure 7-1**.</span></span> <span data-ttu-id="18325-114">Windows 容器上的 ASP .NET Web 窗体应用程序（旧版技术）</span><span class="sxs-lookup"><span data-stu-id="18325-114">ASP.NET Web Forms application (legacy technology) on a Windows Container</span></span>

<span data-ttu-id="18325-115">这是用于浏览和修改目录条目的 Web 窗体应用程序。</span><span class="sxs-lookup"><span data-stu-id="18325-115">This is a Web Forms application that is used to browse and modify the catalog entries.</span></span> <span data-ttu-id="18325-116">Web 窗体依赖项表示此应用程序在不使用 Web 窗体重写后才会在 .NET Core 上运行，另外还会改用 ASP.NET Core MVC。</span><span class="sxs-lookup"><span data-stu-id="18325-116">The Web Forms dependency means this application will not run on .NET Core unless it is rewritten without Web Forms and instead uses ASP.NET Core MVC.</span></span> <span data-ttu-id="18325-117">用户将了解如何无需更改也可以在容器中运行此类应用程序。</span><span class="sxs-lookup"><span data-stu-id="18325-117">You will see how you can run applications like these in containers without changes.</span></span> <span data-ttu-id="18325-118">还会了解如何做最少的更改在混合模式中工作。在该模式下，某些功能已移到单独的微服务，但大多数功能仍保留在整体式应用程序中。</span><span class="sxs-lookup"><span data-stu-id="18325-118">You will also see how you can make minimal changes to work in a hybrid mode where some functionality has been moved into a separate microservice, but most functionality remains in the monolithic application.</span></span>

## <a name="benefits-of-containerizing-a-monolithic-application"></a><span data-ttu-id="18325-119">容器化整体式应用程序的优点</span><span class="sxs-lookup"><span data-stu-id="18325-119">Benefits of containerizing a monolithic application</span></span>

<span data-ttu-id="18325-120">Catalog.WebForms 应用程序可在 eShopOnContainers GitHub 存储库 (<https://github.com/dotnet/eShopOnContainers>) 中获得。</span><span class="sxs-lookup"><span data-stu-id="18325-120">The Catalog.WebForms application is available in the eShopOnContainers GitHub repository (<https://github.com/dotnet/eShopOnContainers>).</span></span> <span data-ttu-id="18325-121">此应用程序是独立的 Web 应用程序，可访问高可用性数据存储。</span><span class="sxs-lookup"><span data-stu-id="18325-121">This application is a standalone web application accessing a high-availability data store.</span></span> <span data-ttu-id="18325-122">即便如此，在容器中运行应用程序仍有其优势。</span><span class="sxs-lookup"><span data-stu-id="18325-122">Even so, there are advantages to running the application in a container.</span></span> <span data-ttu-id="18325-123">创建应用程序的映像。</span><span class="sxs-lookup"><span data-stu-id="18325-123">You create an image for the application.</span></span> <span data-ttu-id="18325-124">自此，每个部署会在相同的环境中运行。</span><span class="sxs-lookup"><span data-stu-id="18325-124">From that point forward, every deployment runs in the same environment.</span></span> <span data-ttu-id="18325-125">每个容器会使用相同的操作系统版本，安装相同版本的依赖项，使用同一个框架，并通过同一个流程生成。</span><span class="sxs-lookup"><span data-stu-id="18325-125">Every container uses the same OS version, has the same version of dependencies installed, uses the same framework, and is built using the same process.</span></span> <span data-ttu-id="18325-126">可在图 7-2 看到 Visual Studio 2017 中加载的应用程序。</span><span class="sxs-lookup"><span data-stu-id="18325-126">You can see the application loaded in Visual Studio 2017 in Figure 7-2.</span></span>

![](./media/image2.png)

<span data-ttu-id="18325-127">**图 7-2**。</span><span class="sxs-lookup"><span data-stu-id="18325-127">**Figure 7-2**.</span></span> <span data-ttu-id="18325-128">Visual Studio 2017 中的目录管理 Web 窗体应用程序</span><span class="sxs-lookup"><span data-stu-id="18325-128">Catalog management Web Forms application in Visual Studio 2017</span></span>

<span data-ttu-id="18325-129">此外，开发人员均可在此一致的环境中运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="18325-129">In addition, developers can all run the application in this consistent environment.</span></span> <span data-ttu-id="18325-130">仅某些版本出现的问题会立即报告给开发人员，而不会出现在暂存或生产环境中。</span><span class="sxs-lookup"><span data-stu-id="18325-130">Issues that only appear with certain versions will appear immediately for developers rather than surfacing in a staging or production environment.</span></span> <span data-ttu-id="18325-131">应用程序在容器中运行后，开发团队的开发环境之间的差异将不那么重要。</span><span class="sxs-lookup"><span data-stu-id="18325-131">Differences between the development environments among the development team matter less once applications run in containers.</span></span>

<span data-ttu-id="18325-132">最后，容器化应用程序具有较为平缓的的横向扩展曲线。</span><span class="sxs-lookup"><span data-stu-id="18325-132">Finally, containerized applications have a flatter scale-out curve.</span></span> <span data-ttu-id="18325-133">你已了解容器化应用如何在 VM 中启用多个容器或如何在物理计算机中启用多个容器。</span><span class="sxs-lookup"><span data-stu-id="18325-133">You have learned how containerized apps enable more containers in a VM or more containers in a physical machine.</span></span> <span data-ttu-id="18325-134">这会转换为需求更少的更高密度的资源。</span><span class="sxs-lookup"><span data-stu-id="18325-134">This translates to higher density and fewer required resources.</span></span>

<span data-ttu-id="18325-135">综上所述，请考虑使用“直接迁移”操作在 Docker 容器中运行旧版整体式应用。</span><span class="sxs-lookup"><span data-stu-id="18325-135">For all these reasons, consider running legacy monolithic apps in a Docker container using a “lift-and-shift” operation.</span></span> <span data-ttu-id="18325-136">“直接迁移”一词说明了任务的范围：将整个应用程序从物理计算机或虚拟机中迁出，再移到容器中。</span><span class="sxs-lookup"><span data-stu-id="18325-136">The phrase “lift and shift” describes the scope of the task: you *lift* the entire application from a physical or virtual machine, and *shift* it into a container.</span></span> <span data-ttu-id="18325-137">理想情况下，不需要对应用程序做任何更改，即可在容器中运行。</span><span class="sxs-lookup"><span data-stu-id="18325-137">In ideal situations, you do not need to make any changes to the application code to run it in a container.</span></span>

## <a name="possible-migration-paths"></a><span data-ttu-id="18325-138">可能的迁移路径</span><span class="sxs-lookup"><span data-stu-id="18325-138">Possible migration paths</span></span>

<span data-ttu-id="18325-139">作为整体式应用程序，Catalog.Webforms 应用程序是一个包含所有代码的 Web 应用程序，其中包括数据访问库。</span><span class="sxs-lookup"><span data-stu-id="18325-139">As a monolithic application, the Catalog.Webforms application is one web application containing all the code, including the data access libraries.</span></span> <span data-ttu-id="18325-140">数据库在单独的高可用性计算机中运行。</span><span class="sxs-lookup"><span data-stu-id="18325-140">The database runs on a separate high-availability machine.</span></span> <span data-ttu-id="18325-141">在示例代码中通过使用模拟目录服务模拟该配置：可以针对该模拟数据运行 Catalog.WebForms 应用程序，模拟纯“直接迁移”方案。</span><span class="sxs-lookup"><span data-stu-id="18325-141">That configuration is simulated in the sample code by using a mock catalog service: you can run the Catalog.WebForms application against that fake data to simulate a pure lift-and-shift scenario.</span></span> <span data-ttu-id="18325-142">此示例演示了最简单的迁移路径，通过该路径可将现有的资产移动到容器中进行运行，无需更改任何代码。</span><span class="sxs-lookup"><span data-stu-id="18325-142">This demonstrates the simplest migration path, where you move existing assets to run in a container without any code changes at all.</span></span> <span data-ttu-id="18325-143">此路径适用于与要移动到微服务的功能交互最少的完整应用程序。</span><span class="sxs-lookup"><span data-stu-id="18325-143">This path is appropriate for applications that are complete and that have minimal interaction with functionality that you are moving to microservices.</span></span>

<span data-ttu-id="18325-144">但是，eShopOnContainers 网站已经使用适用于不同方案的微服务访问数据存储。</span><span class="sxs-lookup"><span data-stu-id="18325-144">However, the eShopOnContainers website is already accessing the data storage using microservices for different scenarios.</span></span> <span data-ttu-id="18325-145">可以另外略微改动目录编辑器，以利用目录微服务，而不是直接访问目录数据存储。</span><span class="sxs-lookup"><span data-stu-id="18325-145">Some small additional changes can be made to the catalog editor to leverage the catalog microservice instead of accessing the catalog data storage directly.</span></span>

<span data-ttu-id="18325-146">这些更改可演示自己应用程序的演变。</span><span class="sxs-lookup"><span data-stu-id="18325-146">These changes demonstrate the continuum for your own applications.</span></span> <span data-ttu-id="18325-147">从不做任何更改将现有应用程序移动到容器，到略微更改，使现有应用程序能够访问某些新的微服务，再到完全重写应用程序，以完全加入一个新的基于微服务的体系结构。</span><span class="sxs-lookup"><span data-stu-id="18325-147">You can do anything from moving an existing application without change into containers, to making small changes that enable existing applications to access some of the new microservices, to completely rewriting an application to fully participate in a new microservice-based architecture.</span></span> <span data-ttu-id="18325-148">正确的路径取决于迁移成本和迁移收益。</span><span class="sxs-lookup"><span data-stu-id="18325-148">The right path depends on both the cost of the migration and the benefits from any migration.</span></span>

## <a name="application-tour"></a><span data-ttu-id="18325-149">应用程序教程</span><span class="sxs-lookup"><span data-stu-id="18325-149">Application tour</span></span>

<span data-ttu-id="18325-150">可以加载 Catalog.WebForms 解决方案，并将该应用程序作为一个独立的应用程序运行。</span><span class="sxs-lookup"><span data-stu-id="18325-150">You can load the Catalog.WebForms solution and run the application as a standalone application.</span></span> <span data-ttu-id="18325-151">在此配置中，而非持久性存储数据库中，该应用程序会使用模拟服务返回数据。</span><span class="sxs-lookup"><span data-stu-id="18325-151">In this configuration, instead of a persistent storage database, the application uses a fake service to return data.</span></span> <span data-ttu-id="18325-152">应用程序使用 Autofac (<https://autofac.org/>) 作为控制反转 (IOC) 容器。</span><span class="sxs-lookup"><span data-stu-id="18325-152">The application uses Autofac (<https://autofac.org/>) as an inversion of control (IOC) container.</span></span> <span data-ttu-id="18325-153">使用依赖项注入 (DI)，可以将应用程序配置为使用模拟数据或实时目录数据服务。</span><span class="sxs-lookup"><span data-stu-id="18325-153">Using Dependency Injection (DI), you can configure the application to use the fake data or the live catalog data service.</span></span> <span data-ttu-id="18325-154">（我们很快会详细介绍 DI。）启动代码会从 web.config 文件中读取 useFake 设置，并将 Autofac 容器配置为注入模拟数据服务或实时目录服务。</span><span class="sxs-lookup"><span data-stu-id="18325-154">(We will explain more about DI shortly.) The startup code reads a useFake setting from the web.config files, and configures the Autofac container to inject either the fake data service or the live catalog service.</span></span> <span data-ttu-id="18325-155">如果在 web.config 文件中使用设置为“false”的 useFake 运行应用程序，则会看到 Web 窗体应用程序显示目录数据。</span><span class="sxs-lookup"><span data-stu-id="18325-155">If you run the application with useFake set to false in the web.config file, you see the Web Forms application displaying the catalog data.</span></span>

<span data-ttu-id="18325-156">使用过 Web 窗体的人应该会非常熟悉在此应用程序中使用的大多数技术。</span><span class="sxs-lookup"><span data-stu-id="18325-156">Most of the techniques used in this application should be very familiar to anyone who has used Web Forms.</span></span> <span data-ttu-id="18325-157">但是，目录微服务会引入两项可能比较陌生的技术：之前提到的依赖项注入 (DI) 和与 Web 窗体中的异步数据存储配合使用。</span><span class="sxs-lookup"><span data-stu-id="18325-157">However, the catalog microservice introduces two techniques that might be unfamiliar: Dependency Injection (DI), which was mentioned earlier, and working with asynchronous data stores in Web Forms.</span></span>

<span data-ttu-id="18325-158">对于分配所有所需资源的写入类，DI 会反转其面向对象的典型策略。</span><span class="sxs-lookup"><span data-stu-id="18325-158">DI inverts the typical object-oriented strategy of writing classes that allocate all needed resources.</span></span> <span data-ttu-id="18325-159">而类会从服务容器请求其依赖项。</span><span class="sxs-lookup"><span data-stu-id="18325-159">Instead, classes request their dependencies from a service container.</span></span> <span data-ttu-id="18325-160">DI 的优点是可以将外部服务替换为模拟服务，以支持测试或其他环境。</span><span class="sxs-lookup"><span data-stu-id="18325-160">The advantage of DI is that you can replace external services with fakes (mocks) to support testing or other environments.</span></span>

<span data-ttu-id="18325-161">DI 容器使用 web.config appSettings 配置控制使用模拟目录数据还是使用正在运行的服务中的实时数据。</span><span class="sxs-lookup"><span data-stu-id="18325-161">The DI container uses the web.config appSettings configuration to control whether to use the fake catalog data or the live data from the running service.</span></span> <span data-ttu-id="18325-162">应用程序会注册生成容器的 HttpModule 对象，然后注册预先请求的处理程序，以注入依赖项。</span><span class="sxs-lookup"><span data-stu-id="18325-162">The application registers an HttpModule object that builds the container and registers a pre-request handler to inject dependencies.</span></span> <span data-ttu-id="18325-163">可以在 Modules/AutoFacHttpModule.cs 文件中看到该代码，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="18325-163">You can see that code in the Modules/AutoFacHttpModule.cs file, which looks like the following example:</span></span>

```cs
private static IContainer CreateContainer()
{
  // Configure AutoFac:
  // Register Containers:

  var settings = WebConfigurationManager.AppSettings;
  var useFake = settings["usefake"];
  bool fake = useFake == "true";
  var builder = new ContainerBuilder();

  if (fake)
  {
    builder.RegisterType<CatalogMockService>()
    .As<ICatalogService>();
  }
  else
  {
    builder.RegisterType<CatalogService>()
    .As<ICatalogService>();
    builder.RegisterType<RequestProvider>()
    .As<IRequestProvider>();
  }

  var container = builder.Build();
  return container;
}

private void InjectDependencies()
{
  if (HttpContext.Current.CurrentHandler is Page page)
  {
    // Get the code-behind class that we may have written
    var pageType = page.GetType().BaseType;

    // Determine if there is a constructor to inject, and grab it
    var ctor = (from c in pageType.GetConstructors()
                where c.GetParameters().Length > 0
                select c).FirstOrDefault();

    if (ctor != null)
    {
      // Resolve the parameters for the constructor
      var args = (from parm in ctor.GetParameters()
                  select Container.Resolve(parm.ParameterType))
                  .ToArray();

      // Execute the constructor method with the arguments resolved
      ctor.Invoke(page, args);
    }

    // Use the Autofac method to inject any
    // properties that can be filled by Autofac
    Container.InjectProperties(page);
  }
}
```

<span data-ttu-id="18325-164">应用程序的页面（Default.aspx.cs 和 EditPage.aspx.cs）定义采用这些依赖项的构造函数。</span><span class="sxs-lookup"><span data-stu-id="18325-164">The application’s pages (Default.aspx.cs and EditPage.aspx.cs) define constructors that take these dependencies.</span></span> <span data-ttu-id="18325-165">请注意，默认构造函数仍存在，并且可以访问。</span><span class="sxs-lookup"><span data-stu-id="18325-165">Note that the default constructor is still present and accessible.</span></span> <span data-ttu-id="18325-166">基础结构需要以下代码。</span><span class="sxs-lookup"><span data-stu-id="18325-166">The infrastructure needs the following code.</span></span>

```cs
protected _Default() { }

public _Default(ICatalogService catalog) => this.catalog = catalog;
```

<span data-ttu-id="18325-167">目录 API 是所有的异步方法。</span><span class="sxs-lookup"><span data-stu-id="18325-167">The catalog APIs are all asynchronous methods.</span></span> <span data-ttu-id="18325-168">Web 窗体现在支持所有数据控件的异步方法。</span><span class="sxs-lookup"><span data-stu-id="18325-168">Web Forms now supports these for all data controls.</span></span> <span data-ttu-id="18325-169">Catalog.WebForms 应用程序将模型绑定用于列表和编辑页面；页面上的控件定义用于指定任务返回异步操作的 SelectMethod、UpdateMethod、InsertMethod 和 DeleteMethod 属性。</span><span class="sxs-lookup"><span data-stu-id="18325-169">The Catalog.WebForms application uses model binding for the list and edit pages; controls on the pages define SelectMethod, UpdateMethod, InsertMethod, and DeleteMethod properties that specify Task-returning asynchronous operations.</span></span> <span data-ttu-id="18325-170">Web 窗体控件知道绑定到控件的方法何时是异步方法。</span><span class="sxs-lookup"><span data-stu-id="18325-170">Web Forms controls understand when the methods bound to a control are asynchronous.</span></span> <span data-ttu-id="18325-171">使用异步选择方法时遇到的唯一限制是不能支持分页。</span><span class="sxs-lookup"><span data-stu-id="18325-171">The only restriction you encounter when using asynchronous select methods is that you cannot support paging.</span></span> <span data-ttu-id="18325-172">分页签名需要输出参数，而异步方法不能具有输出参数。</span><span class="sxs-lookup"><span data-stu-id="18325-172">The paging signature requires an out parameter, and asynchronous methods cannot have out parameters.</span></span> <span data-ttu-id="18325-173">这一技术用于需要来自目录服务的数据的其他页面。</span><span class="sxs-lookup"><span data-stu-id="18325-173">This same technique is used on other pages that require data from the catalog service.</span></span>

<span data-ttu-id="18325-174">目录 Web 窗体应用程序的默认配置使用 catalog.api 服务的模拟实现。</span><span class="sxs-lookup"><span data-stu-id="18325-174">The default configuration for the catalog Web Forms application uses a mock implementation of the catalog.api service.</span></span> <span data-ttu-id="18325-175">此模拟使用其数据的硬编码数据集，通过在开发环境中删除 catalog.api 服务上的依赖项可以简化某些任务。</span><span class="sxs-lookup"><span data-stu-id="18325-175">This mock uses a hard-coded dataset for its data, which simplifies some tasks by removing the dependency on the catalog.api service in development environments.</span></span>

## <a name="lifting-and-shifting"></a><span data-ttu-id="18325-176">直接迁移</span><span class="sxs-lookup"><span data-stu-id="18325-176">Lifting and shifting</span></span>

<span data-ttu-id="18325-177">Visual Studio 为应用程序容器化提供很好的支持。</span><span class="sxs-lookup"><span data-stu-id="18325-177">Visual Studio provides great support for containerizing an application.</span></span> <span data-ttu-id="18325-178">右键单击项目节点，然后选择“添加”和“Docker 支持”。</span><span class="sxs-lookup"><span data-stu-id="18325-178">You right-click the project node and then select **Add** and **Docker Support**.</span></span> <span data-ttu-id="18325-179">Docker 项目模板将一个新项目添加到名为“docker-compose”的解决方案。</span><span class="sxs-lookup"><span data-stu-id="18325-179">The Docker project template adds a new project to the solution called **docker-compose**.</span></span> <span data-ttu-id="18325-180">项目包含编写（或生成）所需映像的 Docker 资产，并开始运行必要的容器，如图 7-3 所示。</span><span class="sxs-lookup"><span data-stu-id="18325-180">The project contains the Docker assets that compose (or build) the images you need, and starts running the necessary containers, as shown in Figure 7-3.</span></span>

<span data-ttu-id="18325-181">在最简单的直接迁移方案中，应用程序将是用于 Web 窗体应用程序的单个服务。</span><span class="sxs-lookup"><span data-stu-id="18325-181">In the simplest lift-and-shift scenarios, the application will be the single service that you use for the Web Forms application.</span></span> <span data-ttu-id="18325-182">模板还会更改启动项目，以指向 docker-compose 项目。</span><span class="sxs-lookup"><span data-stu-id="18325-182">The template also changes your startup project to point to the **docker-compose** project.</span></span> <span data-ttu-id="18325-183">按 Ctrl+F5 或 F5 现可创建 Docker 映像并启动 Docker 容器。</span><span class="sxs-lookup"><span data-stu-id="18325-183">Pressing Ctrl+F5 or F5 now creates the Docker image and launches the Docker container.</span></span>

![](./media/image3.png)

<span data-ttu-id="18325-184">**图 7-3**。</span><span class="sxs-lookup"><span data-stu-id="18325-184">**Figure 7-3**.</span></span> <span data-ttu-id="18325-185">Web 窗体解决方案中的 docker-compose 项目</span><span class="sxs-lookup"><span data-stu-id="18325-185">The **docker-compose** project in the Web Forms solution</span></span>

<span data-ttu-id="18325-186">在运行该解决方案之前，必须确保将 Docker 配置为使用 Windows 容器。</span><span class="sxs-lookup"><span data-stu-id="18325-186">Before you run the solution, you must make sure that you configure Docker to use Windows Containers.</span></span> <span data-ttu-id="18325-187">为此，请右键单击 Windows 中的 Docker 任务栏图标，并选择“切换到 Windows 容器”，如图 7-4 所示。</span><span class="sxs-lookup"><span data-stu-id="18325-187">To do that, you right-click the Docker taskbar icon in Windows and select **Switch to Windows Containers**, as shown in Figure 7-4.</span></span>

![](./media/image4.png)

<span data-ttu-id="18325-188">**图 7-4**。</span><span class="sxs-lookup"><span data-stu-id="18325-188">**Figure 7-4**.</span></span> <span data-ttu-id="18325-189">在 Windows 中从 Docker 任务栏图标切换到 Windows 容器</span><span class="sxs-lookup"><span data-stu-id="18325-189">Switching to Windows Containers from the Docker taskbar icon in Windows</span></span>

<span data-ttu-id="18325-190">如果菜单项显示“切换到 Linux 容器”，则表示已在 Windows 容器中运行 Docker。</span><span class="sxs-lookup"><span data-stu-id="18325-190">If the menu item says **Switch to Linux containers**, you are already running Docker with Windows Containers.</span></span>

<span data-ttu-id="18325-191">运行解决方案会重启 Docker 主机。</span><span class="sxs-lookup"><span data-stu-id="18325-191">Running the solution restarts the Docker host.</span></span> <span data-ttu-id="18325-192">生成时，可以生成 Web 窗体项目的应用程序和 Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="18325-192">When you build, you build the application and the Docker image for the Web Forms project.</span></span> <span data-ttu-id="18325-193">首次执行此操作时，需要相当长的时间。</span><span class="sxs-lookup"><span data-stu-id="18325-193">The first time you do this, it takes considerable time.</span></span> <span data-ttu-id="18325-194">这是因为生成过程会下拉 Windows Server 基础映像和 ASP.NET 的其他映像。</span><span class="sxs-lookup"><span data-stu-id="18325-194">This is because the build process pulls down the base Windows Server image and the additional image for ASP.NET.</span></span> <span data-ttu-id="18325-195">后续的生成和运行循环会快得多。</span><span class="sxs-lookup"><span data-stu-id="18325-195">Subsequent build and run cycles will be much faster.</span></span>

<span data-ttu-id="18325-196">让我们深入了解一下 Docker 项目模板所添加的文件。</span><span class="sxs-lookup"><span data-stu-id="18325-196">Let’s take a deeper look at the files added by the Docker project template.</span></span> <span data-ttu-id="18325-197">它为你创建了多个文件。</span><span class="sxs-lookup"><span data-stu-id="18325-197">It created several files for you.</span></span> <span data-ttu-id="18325-198">Visual Studio 使用这些文件创建 Docker 映像并启动容器。</span><span class="sxs-lookup"><span data-stu-id="18325-198">Visual Studio uses these files to create the Docker image and launch a container.</span></span> <span data-ttu-id="18325-199">可以使用 CLI 的相同文件手动运行 Docker 命令。</span><span class="sxs-lookup"><span data-stu-id="18325-199">You can use the same files from the CLI to run Docker commands manually.</span></span>

<span data-ttu-id="18325-200">以下 Dockerfile 示例显示基于运行 ASP.NET 站点的 Windows ASP.NET 映像生成 Docker 映像时的基本设置。</span><span class="sxs-lookup"><span data-stu-id="18325-200">The following Dockerfile example shows the basic settings for building a Docker image based on the Windows ASP.NET image that runs an ASP.NET site.</span></span>

```
FROM microsoft/aspnet

ARG source

WORKDIR /inetpub/wwwroot

COPY ${source:-obj/Docker/publish} .
```

<span data-ttu-id="18325-201">此 Dockerfile 与创建用于在 Linux 容器中运行 ASP.NET Core 应用程序的 Dockerfile 非常相似。</span><span class="sxs-lookup"><span data-stu-id="18325-201">This Dockerfile will look very similar to those created for running an ASP.NET Core application in Linux containers.</span></span> <span data-ttu-id="18325-202">但是，也有一些重要的区别。</span><span class="sxs-lookup"><span data-stu-id="18325-202">However, there are a few important differences.</span></span> <span data-ttu-id="18325-203">最重要的区别是基础映像为 microsoft/aspnet，它是当前的 Windows Server 映像，包括 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="18325-203">The most important difference is that the base image is microsoft/aspnet, which is the current Windows Server image that includes the .NET Framework.</span></span> <span data-ttu-id="18325-204">其他差异是从源目录复制的目录各不相同。</span><span class="sxs-lookup"><span data-stu-id="18325-204">Other differences are that the directories copied from your source directory are different.</span></span>

<span data-ttu-id="18325-205">docker-compose 项目中的其他文件是生成和配置容器所需的 Docker 资产。</span><span class="sxs-lookup"><span data-stu-id="18325-205">The other files in the **docker-compose** project are the Docker assets needed to build and configure the containers.</span></span> <span data-ttu-id="18325-206">Visual Studio 将各种 docker-compose.yml 文件放在一个节点下，突出显示其使用方式。</span><span class="sxs-lookup"><span data-stu-id="18325-206">Visual Studio puts the various docker-compose.yml files under one node to highlight how they are used.</span></span> <span data-ttu-id="18325-207">基础 docker-compose 文件包含所有配置中常见的指令。</span><span class="sxs-lookup"><span data-stu-id="18325-207">The base docker-compose file contains the directives that are common to all configurations.</span></span> <span data-ttu-id="18325-208">docker-compose.override.yml 文件包含环境变量和开发人员配置的相关替代。</span><span class="sxs-lookup"><span data-stu-id="18325-208">The docker-compose.override.yml file contains environment variables and related overrides for a developer configuration.</span></span> <span data-ttu-id="18325-209">.vs.debug 和 .vs.release 的变量提供的环境设置允许 Visual Studio 附加到正在运行的容器并管理容器。</span><span class="sxs-lookup"><span data-stu-id="18325-209">The variants with .vs.debug and .vs.release provide environment settings that enable Visual Studio to attach to and manage the running container.</span></span>

<span data-ttu-id="18325-210">Visual Studio 集成属于向解决方案添加 Docker 支持时，还可以从命令行使用 docker-compose up 命令生成并运行该集成，如之前几节所示。</span><span class="sxs-lookup"><span data-stu-id="18325-210">While Visual Studio integration is part of adding Docker support to your solution, you can also build and run from the command line, using the docker-compose up command, as you saw in previous sections.</span></span>

## <a name="getting-data-from-the-existing-catalog-net-core-microservice"></a><span data-ttu-id="18325-211">从现有目录 .NET Core 微服务获取数据</span><span class="sxs-lookup"><span data-stu-id="18325-211">Getting data from the existing catalog .NET Core microservice</span></span>

<span data-ttu-id="18325-212">可以将 Web 窗体应用程序配置为使用 eShopOnContainers 目录微服务获取数据，而非使用模拟数据。</span><span class="sxs-lookup"><span data-stu-id="18325-212">You can configure the Web Forms application to use the eShopOnContainers catalog microservice to get data instead of using fake data.</span></span> <span data-ttu-id="18325-213">为此，请编辑 web.config 文件，并将 useFake 键的值设置为“false”。</span><span class="sxs-lookup"><span data-stu-id="18325-213">To do this, you edit the web.config file and set the value of the useFake key to false.</span></span> <span data-ttu-id="18325-214">DI 容器会使用访问实时目录微服务的类，而不会使用返回硬编码数据的类。</span><span class="sxs-lookup"><span data-stu-id="18325-214">The DI container will use the class that accesses the live catalog microservice instead of the class that returns the hard-coded data.</span></span> <span data-ttu-id="18325-215">无需更改任何其他代码。</span><span class="sxs-lookup"><span data-stu-id="18325-215">No other code changes are needed.</span></span>

<span data-ttu-id="18325-216">访问实时目录服务意味着需要更新 docker-compose 项目才能生成目录服务映像并启动目录服务容器。</span><span class="sxs-lookup"><span data-stu-id="18325-216">Accessing the live catalog service does mean you need to update the **docker-compose** project to build the catalog service image and launch the catalog service container.</span></span> <span data-ttu-id="18325-217">Docker CE for Windows 支持 Linux 容器和 Windows 容器，但不能同时支持。</span><span class="sxs-lookup"><span data-stu-id="18325-217">Docker CE for Windows supports both Linux containers and Windows Containers, but not at the same time.</span></span> <span data-ttu-id="18325-218">若要运行目录微服务，需要生成在基于 Windows 的容器上运行目录微服务的映像。</span><span class="sxs-lookup"><span data-stu-id="18325-218">To run the catalog microservice, you need to build an image that runs the catalog microservice on top of a Windows-based container.</span></span> <span data-ttu-id="18325-219">这种方法需要与前面几节不同的微服务项目 Dockerfile。</span><span class="sxs-lookup"><span data-stu-id="18325-219">This approach requires a different Dockerfile for the microservices project than you have seen in earlier sections.</span></span> <span data-ttu-id="18325-220">Dockerfile.windows 文件包含生成目录 API 容器映像所需的配置设置，以便在 Windows 容器上运行，例如使用 Windows Nano Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="18325-220">The Dockerfile.windows file contains the configuration settings to build the catalog API container image so that it runs on a Windows container—for example, to use a Windows Nano Docker image.</span></span>

<span data-ttu-id="18325-221">目录微服务依赖于 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="18325-221">The catalog microservice relies on the SQL Server database.</span></span> <span data-ttu-id="18325-222">因此，还需要使用基于 Windows 的 SQL Server Docker 映像。</span><span class="sxs-lookup"><span data-stu-id="18325-222">Therefore, you need to use a Windows-based SQL Server Docker image as well.</span></span>

<span data-ttu-id="18325-223">更改后，docker-compose 项目需要执行其他操作才能启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="18325-223">After these changes, the docker-compose project does more to start the application.</span></span> <span data-ttu-id="18325-224">项目现在使用基于 Windows 的 SQL Server 映像启动 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="18325-224">The project now starts the SQL Server using the Windows based SQL Server image.</span></span> <span data-ttu-id="18325-225">它会在 Windows 容器中启动目录微服务。</span><span class="sxs-lookup"><span data-stu-id="18325-225">It starts the catalog microservice in a Windows container.</span></span> <span data-ttu-id="18325-226">它还会在 Windows 容器中启动 Web 窗体目录编辑器容器。</span><span class="sxs-lookup"><span data-stu-id="18325-226">And it starts the Web Forms catalog editor container, also in a Windows container.</span></span> <span data-ttu-id="18325-227">如果任何映像需要生成，首先应创建映像。</span><span class="sxs-lookup"><span data-stu-id="18325-227">If any of the images need building, the images are created first.</span></span>

## <a name="development-and-production-environments"></a><span data-ttu-id="18325-228">开发和生产环境</span><span class="sxs-lookup"><span data-stu-id="18325-228">Development and production environments</span></span>

<span data-ttu-id="18325-229">在开发配置与生产配置之间有一些区别。</span><span class="sxs-lookup"><span data-stu-id="18325-229">There are a couple of differences between the development configuration and a production configuration.</span></span> <span data-ttu-id="18325-230">在开发环境中，作为同一 Docker 主机的一部分，在 Windows 容器中运行 Web 窗体应用程序、目录微服务和 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="18325-230">In the development environment, you run the Web Forms application, the catalog microservice, and SQL Server in Windows Containers, as part of the same Docker host.</span></span> <span data-ttu-id="18325-231">前面几节提到了在同一 Docker 主机上部署的 SQL Server 映像作为在基于 Linux 的 Docker 主机上的另一个基于 .NET Core的服务。</span><span class="sxs-lookup"><span data-stu-id="18325-231">In earlier sections, we mentioned SQL Server images deployed in the same Docker host as the other .NET Core-based services on a Linux-based Docker host.</span></span> <span data-ttu-id="18325-232">在同一 Docker 主机（或群集）上运行多个微服务的优点是网络通信更少，容器之间的通信具有较低的延迟。</span><span class="sxs-lookup"><span data-stu-id="18325-232">The advantage of running the multiple microservices in the same Docker host (or cluster) is that there is less network communication and the communication between containers has lower latency.</span></span>

<span data-ttu-id="18325-233">在开发环境中，必须在相同的操作系统中运行所有的容器。</span><span class="sxs-lookup"><span data-stu-id="18325-233">In the development environment, you must run all the containers in the same OS.</span></span> <span data-ttu-id="18325-234">Docker CE for Windows 不支持同时运行基于 Windows 的容器和基于 Linux 的容器。</span><span class="sxs-lookup"><span data-stu-id="18325-234">Docker CE for Windows does not support running Windows- and Linux-based containers at the same time.</span></span> <span data-ttu-id="18325-235">在生产环境中，可以决定是在单个 Docker 主机（或群集）的 Windows 容器中运行目录微服务，还是让 Web 窗体应用程序与在其他 Docker 主机的 Linux 容器中运行的目录微服务实例通信。</span><span class="sxs-lookup"><span data-stu-id="18325-235">In production, you can decide if you want to run the catalog microservice in a Windows container in a single Docker host (or cluster), or have the Web Forms application communicate with an instance of the catalog microservice running in a Linux container on a different Docker host.</span></span> <span data-ttu-id="18325-236">这取决于优化网络延迟所要采用的方法。</span><span class="sxs-lookup"><span data-stu-id="18325-236">It depends on how you want to optimize for network latency.</span></span> <span data-ttu-id="18325-237">在大多数情况下，希望应用程序所依赖的微服务能在同一 Docker 主机（或 swarm）中运行，以便于部署并降低通信延迟。</span><span class="sxs-lookup"><span data-stu-id="18325-237">In most cases, you want the microservices that your applications depend on running in the same Docker host (or swarm) for ease of deployment and lower communication latency.</span></span> <span data-ttu-id="18325-238">在这些配置中，唯一花费较高的通信是微服务实例与永久性数据存储的高可用性服务器之间的通信。</span><span class="sxs-lookup"><span data-stu-id="18325-238">In those configurations, the only costly communications is between the microservice instances and the high-availability servers for the persistent data storage.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="18325-239">[上一页](../net-core-single-containers-linux-windows-server-hosts/index.md)
[下一页](../multi-container-microservice-net-applications/index.md)</span><span class="sxs-lookup"><span data-stu-id="18325-239">[Previous](../net-core-single-containers-linux-windows-server-hosts/index.md)
[Next](../multi-container-microservice-net-applications/index.md)</span></span>
