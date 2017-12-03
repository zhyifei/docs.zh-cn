---
title: "编写使用 OData 服务的 Windows 应用商店应用程序"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: csharp
ms.assetid: 9917a0e9-ec93-49e5-a366-fd39b892eb8b
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: eeee9dcf27d63f5bc40dfdfce1ff7d8104060b6a
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="writing-a-windows-store-app-that-consumes-an-odata-service"></a><span data-ttu-id="6ca2f-102">编写使用 OData 服务的 Windows 应用商店应用程序</span><span class="sxs-lookup"><span data-stu-id="6ca2f-102">Writing a Windows Store App that consumes an OData Service</span></span>
<span data-ttu-id="6ca2f-103">Windows 8 引入了新的应用程序类型： Windows 应用商店应用。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-103">Windows 8 introduces a new type of application: the Windows Store app.</span></span> <span data-ttu-id="6ca2f-104">Windows 应用商店应用程序具有全新的外观，可在各种设备上运行并在 Windows 应用商店中有售。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-104">Windows Store apps have a brand new look and feel, run on a variety of devices, and are made available on the Windows Store.</span></span> <span data-ttu-id="6ca2f-105">本主题说明如何编写使用 OData 服务（特别是 NetFlix Catalog OData 服务）的 Windows 应用商店应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-105">This topic describes how to write a Windows Store app that consumes an OData service, specifically the NetFlix Catalog OData service.</span></span> <span data-ttu-id="6ca2f-106">有关 Windows 应用商店应用的详细信息，请阅读[Windows 应用商店应用入门](http://msdn.microsoft.com/library/windows/apps/br211386.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-106">For more information about Windows Store Apps, please read [Getting Started with Windows Store apps](http://msdn.microsoft.com/library/windows/apps/br211386.aspx).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6ca2f-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="6ca2f-107">Prerequisites</span></span>  
  
1.  [<span data-ttu-id="6ca2f-108">Microsoft Windows 8</span><span class="sxs-lookup"><span data-stu-id="6ca2f-108">Microsoft Windows 8</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=266654)  
  
2.  [<span data-ttu-id="6ca2f-109">Microsoft Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="6ca2f-109">Microsoft Visual Studio 2012</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=266655)  
  
3.  [<span data-ttu-id="6ca2f-110">WCF 数据服务</span><span class="sxs-lookup"><span data-stu-id="6ca2f-110">WCF Data Services</span></span>](http://msdn.microsoft.com/data/bb931106)  
  
#### <a name="creating-the-default-windows-store-grid-application"></a><span data-ttu-id="6ca2f-111">创建默认 Windows 应用商店网格应用程序</span><span class="sxs-lookup"><span data-stu-id="6ca2f-111">Creating the default Windows Store Grid Application</span></span>  
  
1.  <span data-ttu-id="6ca2f-112">使用 C# 和 XAML 创建新的 Windows 应用商店网格应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-112">Create a new Windows Store Grid Application using C# and XAML.</span></span> <span data-ttu-id="6ca2f-113">将该应用程序命名为 OData.WindowsStore.NetflixDemo：</span><span class="sxs-lookup"><span data-stu-id="6ca2f-113">Name the application OData.WindowsStore.NetflixDemo:</span></span>  
  
     <span data-ttu-id="6ca2f-114">![新建项目对话框](../../../../docs/framework/data/wcf/media/win8clientcreatenewproject.png "Win8ClientCreateNewProject")</span><span class="sxs-lookup"><span data-stu-id="6ca2f-114">![New Project Dialog](../../../../docs/framework/data/wcf/media/win8clientcreatenewproject.png "Win8ClientCreateNewProject")</span></span>  
  
2.  <span data-ttu-id="6ca2f-115">打开 Package.appxmanifest，然后在“显示名称”文本框中输入一个友好名称。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-115">Open the Package.appxmanifest and enter a friendly name in the Display name text box.</span></span> <span data-ttu-id="6ca2f-116">这指定与 Windows 8 搜索功能一起使用的应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-116">This specifies the application name used with the Windows 8 search functionality.</span></span>  
  
     <span data-ttu-id="6ca2f-117">![应用程序清单文件](../../../../docs/framework/data/wcf/media/appxmanifest.png "appxmanifest")</span><span class="sxs-lookup"><span data-stu-id="6ca2f-117">![Application manifest file](../../../../docs/framework/data/wcf/media/appxmanifest.png "appxmanifest")</span></span>  
  
3.  <span data-ttu-id="6ca2f-118">输入中的友好名称\<AppName > App.xaml 文件中的元素。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-118">Enter a friendly name in the \<AppName> element in the App.xaml file.</span></span> <span data-ttu-id="6ca2f-119">这设置在应用程序启动时显示的应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-119">This sets the application name that is displayed when the application is launched:</span></span>  
  
     <span data-ttu-id="6ca2f-120">![App.xaml 文件](../../../../docs/framework/data/wcf/media/appxaml.png "appxaml")</span><span class="sxs-lookup"><span data-stu-id="6ca2f-120">![App.xaml file](../../../../docs/framework/data/wcf/media/appxaml.png "appxaml")</span></span>  
  
4.  <span data-ttu-id="6ca2f-121">生成并启动该应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-121">Build and launch the application.</span></span> <span data-ttu-id="6ca2f-122">您首先看到的是应用程序的初始屏幕。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-122">You first see the application’s splash screen.</span></span> <span data-ttu-id="6ca2f-123">下面的屏幕快照显示默认初始屏幕。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-123">The screenshot below displays the default splash screen.</span></span> <span data-ttu-id="6ca2f-124">使用的图像存储在项目的 Assets 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-124">The image used is stored in the project’s Assets folder.</span></span>  
  
     <span data-ttu-id="6ca2f-125">![默认应用程序初始屏幕](../../../../docs/framework/data/wcf/media/defualtappsplash.png "defualtAppSplash")</span><span class="sxs-lookup"><span data-stu-id="6ca2f-125">![The default app splash screen](../../../../docs/framework/data/wcf/media/defualtappsplash.png "defualtAppSplash")</span></span>  
  
     <span data-ttu-id="6ca2f-126">然后，将显示该应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-126">Then the application will be displayed.</span></span>  
  
     <span data-ttu-id="6ca2f-127">![默认应用程序](../../../../docs/framework/data/wcf/media/defaultapplication.png "DefaultApplication")</span><span class="sxs-lookup"><span data-stu-id="6ca2f-127">![The default application](../../../../docs/framework/data/wcf/media/defaultapplication.png "DefaultApplication")</span></span>  
  
     <span data-ttu-id="6ca2f-128">默认应用程序在 SampleDataSource.cs 中定义一组类：SampleDataGroup 和 SampleDataItem，它们都从 SampleDataCommon 派生，而 SampleDataCommon 则从 BindableBase 派生。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-128">The default application defines a set of classes in SampleDataSource.cs: SampleDataGroup and SampleDataItem, both of which are derived from SampleDataCommon, which itself is derived from BindableBase.</span></span> <span data-ttu-id="6ca2f-129">SampleDataGroup 和 SampleDataItem 绑定到默认 GridView。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-129">SampleDataGroup and SampleDataItem are bound to the default GridView.</span></span> <span data-ttu-id="6ca2f-130">SampleDataSource.cs 位于 NetflixDemois 项目的 DataModel 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-130">SampleDataSource.cs is located in the DataModel folder within the NetflixDemo project.</span></span> <span data-ttu-id="6ca2f-131">该应用程序显示分组的集合。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-131">The application displays a grouped collection.</span></span> <span data-ttu-id="6ca2f-132">每个组包含任意数量的项，分别由 SampleDataGroup 和 SampleDataItem 表示。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-132">Each group contains any number of items, represented by SampleDataGroup and SampleDataItem, respectively.</span></span> <span data-ttu-id="6ca2f-133">在前面的屏幕快照中，您可以看到称为项目 Group Title 1 的组，该组中的所有项在一起显示。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-133">In the previous screen shot you can see a group called Group Title 1 and all of the items in the group displayed together.</span></span>  
  
     <span data-ttu-id="6ca2f-134">应用程序的主页是 GroupedItemsPage.xaml。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-134">The main page of the application is GroupedItemsPage.xaml.</span></span> <span data-ttu-id="6ca2f-135">它包含一个 GridView， 后者显示 SampleDataSource.cs 类创建的示例数据。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-135">It contains a GridView that displays the sample data created by the SampleDataSource.cs class.</span></span> <span data-ttu-id="6ca2f-136">在调用 rootFrame.Navigate 时，由 App.xaml.cs 加载 GroupedItemsPage：</span><span class="sxs-lookup"><span data-stu-id="6ca2f-136">The GroupedItemsPage is loaded by the App.xaml.cs in a call to rootFrame.Navigate:</span></span>  
  
    ```csharp  
    if (!rootFrame.Navigate(typeof(GroupedItemsPage), "AllGroups"))  
    {  
        throw new Exception("Failed to create initial page");  
    }  
    ```  
  
     <span data-ttu-id="6ca2f-137">这导致 GroupedItemsPage 实例化且调用其 LoadState 方法。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-137">This causes the GroupedItemsPage to be instantiated and it’s LoadState method is called.</span></span> <span data-ttu-id="6ca2f-138">LoadState 导致创建静态 SampleDataSource 实例，该实例创建 SampleDataGroup 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-138">LoadState causes the static SampleDataSource instance to be created, which creates a collection of SampleDataGroup objects.</span></span> <span data-ttu-id="6ca2f-139">每个 SampleDataGroup 对象包含 SampleDataItem 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-139">Each SampleDataGroup object contains a collection of SampleDataItem objects.</span></span> <span data-ttu-id="6ca2f-140">LoadState 在 DefaultViewModel 中存储 SampleDataGroup 对象的集合：</span><span class="sxs-lookup"><span data-stu-id="6ca2f-140">LoadState stores the collection of SampleDataGroup objects in the DefaultViewModel:</span></span>  
  
    ```csharp  
    protected override void LoadState(Object navigationParameter, Dictionary<String, Object> pageState)  
    {  
        var sampleDataGroups = SampleDataSource.GetGroups((String)navigationParameter);  
        this.DefaultViewModel["Groups"] = sampleDataGroups;  
    }  
    ```  
  
     <span data-ttu-id="6ca2f-141">然后将 DefaultViewModel 绑定到 GridView。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-141">The DefaultViewModel is then bound to the GridView.</span></span> <span data-ttu-id="6ca2f-142">配置数据绑定时，将在 GroupedItemsPage.xaml 文件中引用它。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-142">This is referenced in the GroupedItemsPage.xaml file when configuring the data binding.</span></span>  
  
    ```xaml
    <CollectionViewSource  
                x:Name="groupedItemsViewSource"  
                Source="{Binding Groups}"  
                IsSourceGrouped="true"  
                ItemsPath="TopItems"  
                d:Source="{Binding AllGroups, Source={d:DesignInstance Type=data:SampleDataSource, IsDesignTimeCreatable=True}}"/>  
    ```  
  
     <span data-ttu-id="6ca2f-143">CollectionViewSource 用作处理分组集合的代理。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-143">The CollectionViewSource is used as a proxy for handling grouped collections.</span></span> <span data-ttu-id="6ca2f-144">绑定发生时，它遍历 SampleDataGroup 对象的集合以填充 GridView。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-144">When binding occurs, it iterates through the collection of SampleDataGroup objects to populate the GridView.</span></span>  <span data-ttu-id="6ca2f-145">ItemsPath 特性通知 CollectionViewSource 要使用每个 SampleDataGroup 对象的哪些属性来查找它包含的 SampleDataItem。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-145">The ItemsPath attribute tells the CollectionViewSource what property on each SampleDataGroup object to use to find the SampleDataItems it contains.</span></span> <span data-ttu-id="6ca2f-146">在本示例中，每个 SampleDataGroup 对象包含 SampleDataItem 对象的 TopItems 集合。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-146">In this case each SampleDataGroup object contains a TopItems collection of SampleDataItem objects.</span></span>  
  
     <span data-ttu-id="6ca2f-147">对于 Netflix 应用程序，按风格将影片分组。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-147">For the Netflix application, movies are grouped by genre.</span></span> <span data-ttu-id="6ca2f-148">因此，应用程序显示很多风格以及属于各个风格的影片。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-148">So the application displays a number of genres and a list of movies within that genre.</span></span>  
  
#### <a name="add-a-service-reference-to-the-netflix-odata-service"></a><span data-ttu-id="6ca2f-149">向 Netflix OData 服务添加服务引用</span><span class="sxs-lookup"><span data-stu-id="6ca2f-149">Add a Service Reference to the Netflix OData Service</span></span>  
  
1.  <span data-ttu-id="6ca2f-150">在调用 Netflix OData 服务前，需要添加服务引用。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-150">Before we can make any calls to the Netflix OData service we need to add a service reference.</span></span> <span data-ttu-id="6ca2f-151">在解决方案资源管理器中，右击该项目，并选择“添加服务引用…”。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-151">Right-click the project in the Solution Explorer and select Add Service Reference…</span></span>  
  
     <span data-ttu-id="6ca2f-152">![添加服务引用对话框](../../../../docs/framework/data/wcf/media/addservicereferenceodata.png "AddServiceReferenceOData")</span><span class="sxs-lookup"><span data-stu-id="6ca2f-152">![Add Service Reference Dialog](../../../../docs/framework/data/wcf/media/addservicereferenceodata.png "AddServiceReferenceOData")</span></span>  
  
2.  <span data-ttu-id="6ca2f-153">在地址栏中输入 Netflix OData 服务的 URL，并单击“访问”。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-153">Enter the URL for the Netflix OData service in the Address bar and click Go.</span></span> <span data-ttu-id="6ca2f-154">将服务引用的命名空间设置为 Netflix，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-154">Set the Namespace of the service reference to Netflix and click OK.</span></span>  
  
     <span data-ttu-id="6ca2f-155">![添加服务引用错误](../../../../docs/framework/data/wcf/media/addservicereferenceerror.png "AddServiceReferenceError")</span><span class="sxs-lookup"><span data-stu-id="6ca2f-155">![Add Service Reference Error](../../../../docs/framework/data/wcf/media/addservicereferenceerror.png "AddServiceReferenceError")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6ca2f-156">如果尚未安装[WCF 数据服务工具为 Windows 应用商店应用](http://go.microsoft.com/fwlink/p/?LinkId=266652)，系统将提示您提供一条消息，如上述的那个。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-156">If you have not yet installed [WCF Data Services Tools for Windows Store Apps](http://go.microsoft.com/fwlink/p/?LinkId=266652), you will be prompted with a message such as the one above.</span></span> <span data-ttu-id="6ca2f-157">您需要下载并安装链接中引用的工具以继续。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-157">You will need to download and install the tools referenced in the link to continue.</span></span>  
  
 <span data-ttu-id="6ca2f-158">添加服务引用将强类型化的类，WCF 数据服务将使用该类分析 Netflix OData 服务返回的 OData。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-158">Adding a service reference generates strongly typed classes that WCF Data Services will use to parse the OData returned by the Netflix OData service.</span></span> <span data-ttu-id="6ca2f-159">在 SampleDataSource.cs 中定义的类可以绑定到 GridView，因此我们需要将数据从生成的 OData 客户端类传输到在 SampleDataSource.cs 中定义的可绑定类。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-159">The classes defined in SampleDataSource.cs can be bound to the GridView so we need to transfer the data from the generated OData client classes into the bindable classes defined in SampleDataSource.cs.</span></span>  <span data-ttu-id="6ca2f-160">为此，我们需要对 SampleDataSource.cs 中定义的数据模型进行一下更改。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-160">In order to do this, we need to make some changes to the data model defined in SampleDataSource.cs.</span></span>  
  
#### <a name="update-the-data-model-for-the-application"></a><span data-ttu-id="6ca2f-161">更新应用程序的数据模型</span><span class="sxs-lookup"><span data-stu-id="6ca2f-161">Update the data model for the application</span></span>  
  
1.  <span data-ttu-id="6ca2f-162">中的代码替换 SampleDataSource.cs 中的现有代码[此主题](https://gist.github.com/3419288)。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-162">Replace the existing code in SampleDataSource.cs with the code from [this gist](https://gist.github.com/3419288).</span></span> <span data-ttu-id="6ca2f-163">更新的代码向 SampleDataSource 类添加一个 LoadMovies 方法，该方法将对 Netflix OData 服务执行一个查询并填充风格列表 (allGroups) 和在每个风格内填充影片列表。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-163">The updated code adds a LoadMovies method (to the SampleDataSource class)  that performs a query against the Netflix OData service and populates a list of genres (allGroups) and within each genre a list of movies.</span></span> <span data-ttu-id="6ca2f-164">SampleDataGroup 类用于表示一种风格，SampleDataItem 类用于表示一个影片。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-164">The SampleDataGroup class is used to represent a genre and the SampleDataItem class is used to represent a movie.</span></span>  
  
    ```csharp  
    public static async void LoadMovies()  
    {  
        IEnumerable<Title> titles = await ((DataServiceQuery<Title>)Context.Titles  
            .Expand("Genres,AudioFormats,AudioFormats/Language,Awards,Cast")  
            .Where(t => t.Rating == "PG")  
            .OrderByDescending(t => t.ReleaseYear)  
            .Take(300)).ExecuteAsync();  
  
        foreach (Title title in titles)  
        {  
            foreach (Genre netflixGenre in title.Genres)  
            {  
                SampleDataGroup genre = GetGroup(netflixGenre.Name);  
                if (genre == null)  
                {  
                    genre = new SampleDataGroup(netflixGenre.Name, netflixGenre.Name, String.Empty, title.BoxArt.LargeUrl, String.Empty);  
                    Instance.AllGroups.Add(genre);  
                }  
                var content = new StringBuilder();  
                // Write additional things to content here if you want them to display in the item detail.  
                genre.Items.Add(new SampleDataItem(title.Id, title.Name, String.Format("{0}rnrn{1} ({2})", title.Synopsis, title.Rating, title.ReleaseYear), title.BoxArt.HighDefinitionUrl ?? title.BoxArt.LargeUrl, "Description", content.ToString()));  
            }  
        }  
    }  
    ```  
  
     <span data-ttu-id="6ca2f-165">[基于任务的异步模式](http://go.microsoft.com/fwlink/p/?LinkId=266651)(TAP) 用于以异步方式获取 300 (Take) 最新 (OrderByDescending) 已进行 PG 评定的 (Where) 影片从 Netflix。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-165">The [Task-based Asynchronous Pattern](http://go.microsoft.com/fwlink/p/?LinkId=266651) (TAP) is used to asynchronously get 300 (Take) recent (OrderByDescending) PG-rated (Where) movies back from Netflix.</span></span> <span data-ttu-id="6ca2f-166">其余代码从 OData 源返回的实体构造 SimpleDataItems 和 SimpleDataGroups。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-166">The rest of the code constructs SimpleDataItems and SimpleDataGroups from the entities that were returned in the OData feed.</span></span>  
  
     <span data-ttu-id="6ca2f-167">SampleDataSource 类还实现简单的搜索方法。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-167">The SampleDataSource class also implements a simple search method.</span></span> <span data-ttu-id="6ca2f-168">在本示例中，它对加载的影片执行简单的内存中搜索。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-168">In this case, it does a simple in-memory search of the loaded movies.</span></span>  
  
    ```csharp  
    public static IEnumerable<SampleDataItem> Search(string searchString)  
    {  
            var regex = new Regex(searchString, RegexOptions.CultureInvariant | RegexOptions.IgnoreCase | RegexOptions.IgnorePatternWhitespace);  
            return Instance.AllGroups  
                .SelectMany(g => g.Items)  
                .Where(m => regex.IsMatch(m.Title) || regex.IsMatch(m.Subtitle))  
                    .Distinct(new SampleDataItemComparer());  
    }  
    ```  
  
     <span data-ttu-id="6ca2f-169">在 SampleDataSource.cs 中，还定义了称为 ExtensionMethods 的类。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-169">Also in SampleDataSource.cs a class called ExtensionMethods is defined.</span></span> <span data-ttu-id="6ca2f-170">这些扩展方法使用 TAP 模式以允许 SampleDataSource 在不阻塞 UI 的情况下执行 OData 查询。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-170">Each of these extension methods uses the TAP pattern to allow the SampleDataSource to execute an OData query without blocking the UI.</span></span> <span data-ttu-id="6ca2f-171">例如，以下代码使用 Task.Factory.FromAsync 方法实现 TAP：</span><span class="sxs-lookup"><span data-stu-id="6ca2f-171">For example, the following code uses the Task.Factory.FromAsync method to implement TAP.</span></span>  
  
    ```csharp  
    public static async Task<IEnumerable<T>> ExecuteAsync<T>(this DataServiceQuery<T> query)  
    {  
        return await Task.Factory.FromAsync<IEnumerable<T>>(query.BeginExecute(null, null), query.EndExecute);  
    }  
    ```  
  
     <span data-ttu-id="6ca2f-172">在默认应用程序中，应用程序的主页是 GroupedItemsPage。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-172">As in the default application, the main page of the application is GroupedItemsPage.</span></span> <span data-ttu-id="6ca2f-173">不过，此时它显示从 Netflix 按风格分组检索的影片。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-173">This time, however, it displays the movies retrieved from Netflix grouped by genre.</span></span>  <span data-ttu-id="6ca2f-174">GroupedItemsPage 实例化时，调用其 LoadState 方法。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-174">When the GroupedItemsPage is instantiated, its LoadState method is called.</span></span> <span data-ttu-id="6ca2f-175">LoadState 导致创建静态 SampleDataSource 实例，并前文所述调用 Netflix OData 服务。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-175">LoadState causes the static SampleDataSource instance to be created, making a call to the Netflix OData service as discussed previously.</span></span> <span data-ttu-id="6ca2f-176">LoadState 在 DefaultViewModel 中存储风格（SampleDataGroup 对象）的集合：</span><span class="sxs-lookup"><span data-stu-id="6ca2f-176">LoadState stores the collection of genres (SampleDataGroup objects) in the DefaultViewModel:</span></span>  
  
    ```csharp  
    protected override void LoadState(Object navigationParameter, Dictionary<String, Object> pageState)  
    {  
  
        var sampleDataGroups = SampleDataSource.GetGroups((String)navigationParameter);  
        this.DefaultViewModel["Groups"] = sampleDataGroups;  
    }  
    ```  
  
     <span data-ttu-id="6ca2f-177">如前文所述，然后使用 DefaultViewModel 将数据绑定到 GridView。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-177">As described previously, the DefaultViewModel is then used to bind the data to the GridView.</span></span>  
  
#### <a name="add-a-search-contract-to-allow-the-application-to-participate-in-windows-search"></a><span data-ttu-id="6ca2f-178">添加搜索协定以允许应用程序参与 Windows 搜索</span><span class="sxs-lookup"><span data-stu-id="6ca2f-178">Add a search contract to allow the application to participate in Windows search</span></span>  
  
1.  <span data-ttu-id="6ca2f-179">向应用程序添加搜索协定。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-179">Add a search contract to the application.</span></span> <span data-ttu-id="6ca2f-180">这允许应用程序集成与 Windows 8 搜索功能集成。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-180">This allows the application to integrate with the Windows 8 search experience.</span></span> <span data-ttu-id="6ca2f-181">将搜索协定命名为 SearchResultsPage.xaml</span><span class="sxs-lookup"><span data-stu-id="6ca2f-181">Name the search contract SearchResultsPage.xaml</span></span>  
  
     <span data-ttu-id="6ca2f-182">![添加搜索协定](../../../../docs/framework/data/wcf/media/addsearchcontract.png "AddSearchContract")</span><span class="sxs-lookup"><span data-stu-id="6ca2f-182">![Add a search contract](../../../../docs/framework/data/wcf/media/addsearchcontract.png "AddSearchContract")</span></span>  
  
2.  <span data-ttu-id="6ca2f-183">通过删除 queryText 周围迁入的引号，修改 SearchResultsPage.xaml.cs 的第 58 行：</span><span class="sxs-lookup"><span data-stu-id="6ca2f-183">Modify line 58 of SearchResultsPage.xaml.cs by removing the embedded quotes around queryText.</span></span>  
  
    ```csharp  
    // Communicate results through the view model  
    this.DefaultViewModel["QueryText"] = queryText;  
    this.DefaultViewModel["Filters"] = filterList;  
    this.DefaultViewModel["ShowFilters"] = filterList.Count > 1;  
    ```  
  
3.  <span data-ttu-id="6ca2f-184">将第 81 行的以下两行代码插入 SearchResultsPage.xaml.cs 以检索搜索结果。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-184">Insert the following two lines of code at line 81 in SearchResultsPage.xaml.cs to retrieve the search results.</span></span>  
  
    ```csharp  
    // TODO: Respond to the change in active filter by setting this.DefaultViewModel["Results"]  
                    //       to a collection of items with bindable Image, Title, Subtitle, and Description properties  
                    var searchValue = (string)this.DefaultViewModel["QueryText"];  
                    this.DefaultViewModel["Results"] = new List<SampleDataItem>(SampleDataSource.Search(searchValue));  
    ```  
  
 <span data-ttu-id="6ca2f-185">用户调用 Windows 搜索时，键入一个搜索词然后在搜索栏点按“Netflix 演示应用程序”图标，执行 SearchResultsPage 的 LoadState 方法。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-185">When a user invokes Windows search, types in a search term and then touches the Netflix Demo app icon in the search bar, the LoadState method of the SearchResultsPage is executed.</span></span> <span data-ttu-id="6ca2f-186">发送到 LoadState 的导航参数包含查询文本。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-186">The navigation parameter sent to LoadState contains the query text.</span></span> <span data-ttu-id="6ca2f-187">接着调用 Filter_SelectionChanged 方法，该方法调用 SampleDataSourceen 类的 Search 方法。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-187">Next the Filter_SelectionChanged method is called which then calls the Search method on the SampleDataSource class.</span></span> <span data-ttu-id="6ca2f-188">返回结果并将其显示在 SearchResultsPage.xaml 页。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-188">The results are returned and displayed in the SearchResultsPage.xaml page.</span></span>  
  
```csharp  
/// <summary>  
        /// Invoked when a filter is selected using the ComboBox in snapped view state.  
        /// </summary>  
        /// <param name="sender">The ComboBox instance.</param>  
        /// <param name="e">Event data describing how the selected filter was changed.</param>  
        void Filter_SelectionChanged(object sender, SelectionChangedEventArgs e)  
        {  
            // Determine what filter was selected  
            var selectedFilter = e.AddedItems.FirstOrDefault() as Filter;  
            if (selectedFilter != null)  
            {  
                // Mirror the results into the corresponding Filter object to allow the  
                // RadioButton representation used when not snapped to reflect the change  
                selectedFilter.Active = true;  
  
                // TODO: Respond to the change in active filter by setting this.DefaultViewModel["Results"]  
                //       to a collection of items with bindable Image, Title, Subtitle, and Description properties  
                var searchValue = (string)this.DefaultViewModel["QueryText"];  
                this.DefaultViewModel["Results"] = new List<SampleDataItem>(SampleDataSource.Search(searchValue));  
  
                // Ensure results are found  
                object results;  
                ICollection resultsCollection;  
                if (this.DefaultViewModel.TryGetValue("Results", out results) &&  
                    (resultsCollection = results as ICollection) != null &&  
                    resultsCollection.Count != 0)  
                {  
                    VisualStateManager.GoToState(this, "ResultsFound", true);  
                    return;  
                }  
            }  
  
            // Display informational text when there are no search results.  
            VisualStateManager.GoToState(this, "NoResultsFound", true);  
        }  
```  
  
 <span data-ttu-id="6ca2f-189">有关详细信息将搜索集成到应用程序，请参阅[搜索： 将集成到 Windows 8 搜索功能](http://go.microsoft.com/fwlink/p/?LinkId=266650)。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-189">For more information on integrating search into an application see, [Search: integrating into the Windows 8 search experience](http://go.microsoft.com/fwlink/p/?LinkId=266650).</span></span>  
  
## <a name="run-the-application"></a><span data-ttu-id="6ca2f-190">运行此应用程序</span><span class="sxs-lookup"><span data-stu-id="6ca2f-190">Run the application</span></span>  
 <span data-ttu-id="6ca2f-191">按 F5 启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-191">Launch the application by pressing F5.</span></span> <span data-ttu-id="6ca2f-192">请注意，应用程序启动后，需要几秒钟加载这些图像。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-192">Note that it will take a few seconds to load the images upon application launch.</span></span> <span data-ttu-id="6ca2f-193">此外，您的第一个搜索尝试可能不返回任何结果。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-193">Also, your first search attempt may not return any results.</span></span> <span data-ttu-id="6ca2f-194">在实际应用程序中，您需要处理这些问题。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-194">In a real-world application, you would want to deal with both of these issues.</span></span>  
  
 <span data-ttu-id="6ca2f-195">应用程序调用 Netflix OData 服务，接收生成的 OData 客户端类中的数据，然后将该数据传输到可绑定的数据类（SampleDataSource、SampleDataGroup 和 SampleDataItem）。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-195">The application calls the Netflix OData service, receives the data in the generated OData client classes and then transfers that data to bindable data classes (SampleDataSource, SampleDataGroup, and SampleDataItem).</span></span> <span data-ttu-id="6ca2f-196">它使用这些可绑定的类将数据绑定到 GridView。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-196">It uses these bindable classes to bind the data to the GridView.</span></span> <span data-ttu-id="6ca2f-197">如果你不熟悉 XAML 数据绑定的工作原理，请参阅[如何列表或网格 （使用 C# / VB/c + + 和 XAML 的 Windows 应用商店应用） 中的项进行分组](http://msdn.microsoft.com/library/windows/apps/xaml/hh780627)。</span><span class="sxs-lookup"><span data-stu-id="6ca2f-197">If you are unfamiliar with how XAML databinding works see [How to group items in a list or grid (Windows Store apps using C#/VB/C++ and XAML)](http://msdn.microsoft.com/library/windows/apps/xaml/hh780627).</span></span>
