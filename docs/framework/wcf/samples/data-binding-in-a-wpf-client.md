---
title: "Windows Presentation Foundation 客户端中的数据绑定"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb8c8293-5973-4aef-9b07-afeff5d3293c
caps.latest.revision: "21"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0fba3f83bbff42f570ce6da1544d2c0f1ea32393
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="data-binding-in-a-windows-presentation-foundation-client"></a><span data-ttu-id="8e0a2-102">Windows Presentation Foundation 客户端中的数据绑定</span><span class="sxs-lookup"><span data-stu-id="8e0a2-102">Data Binding in a Windows Presentation Foundation Client</span></span>
<span data-ttu-id="8e0a2-103">本示例演示 Windows Presentation Foundation (WPF) 客户端中数据绑定的用法。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-103">This sample demonstrates the use of data binding in a Windows Presentation Foundation (WPF) client.</span></span> <span data-ttu-id="8e0a2-104">本示例使用一个 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务，该服务随机生成一个要返回到客户端的唱片集数组。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-104">The sample uses a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service that randomly generates an array of albums to return to the client.</span></span> <span data-ttu-id="8e0a2-105">每个唱片集都有名称、价格和唱片集曲目列表。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-105">Each album has a name, a price, and a list of album tracks.</span></span> <span data-ttu-id="8e0a2-106">唱片集曲目具有名称和持续时间。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-106">The album tracks have a name and duration.</span></span> <span data-ttu-id="8e0a2-107">服务返回的信息自动绑定到由 [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] 客户端提供的用户接口 (UI)。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-107">The information that is returned by the service is automatically bound to the user interface (UI) provided by the [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)] client.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e0a2-108">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="8e0a2-109">使用数据绑定可以将数据源自动绑定到 UI。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-109">Data binding allows a data source to be automatically bound to a UI.</span></span> <span data-ttu-id="8e0a2-110">这简化了编程模型，因为它不需要您以编程方式使用数据对象中的数据或数据对象数组中的数据更新每个 UI 元素。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-110">This simplifies the programming model because it does not require that you programmatically update each UI element with the data from a data object or an array of data objects.</span></span> <span data-ttu-id="8e0a2-111">您可以将对象绑定到单个 UI 元素或将数组绑定到采用多个输入的控件（如 `ListBox`）。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-111">You can bind an object to a single UI element or an array to a control that takes multiple inputs, such as a `ListBox`.</span></span> <span data-ttu-id="8e0a2-112">下面的代码演示如何将数据绑定到 UI 元素的 `DataContext`。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-112">The following code shows how to bind data to the `DataContext` of a UI element.</span></span>  
  
```  
// Event handler executed when call is complete  
void client_GetAlbumListCompleted(object sender, GetAlbumListCompletedEventArgs e)  
{  
    // This is on the UI thread, myPanel can be accessed directly  
    myPanel.DataContext = e.Result;   
}  
```  
  
 <span data-ttu-id="8e0a2-113">在前面的示例中，将名为 `DataContext` 的 `grid` 布局元素的 `myPanel` 设置为 `GetAlbumList` 方法返回的数据。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-113">In the previous sample, the `DataContext` for the `grid` layout element named `myPanel` is set to the data returned by the `GetAlbumList` method.</span></span> <span data-ttu-id="8e0a2-114">`DataContext` 使元素可以从它们的父元素继承有关用于绑定的数据源以及绑定的其他特征（例如路径）的信息。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-114">The `DataContext` allows elements to inherit information from their parent elements about the data source that is used for binding, as well as other characteristics of the binding such as the path.</span></span> <span data-ttu-id="8e0a2-115">每次更新服务器上的数据时，必须执行该代码行。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-115">The line of code must be executed every time the data on the server is updated.</span></span> <span data-ttu-id="8e0a2-116">例如，初始化窗口时和添加新唱片集时执行该代码行。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-116">For example, it is executed when the window is initialized and when a new album is added.</span></span>  
  
 <span data-ttu-id="8e0a2-117">在下面的示例 XAML 代码中，`ListBox` 指定 `ItemsSource="{Binding }"`。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-117">In the following sample XAML code, the `ListBox` specifies `ItemsSource="{Binding }"`.</span></span>  
  
```xml  
<ListBox   
          ItemTemplate="{StaticResource AlbumStyle}"  
          ItemsSource="{Binding }"   
          IsSynchronizedWithCurrentItem="true" />  
```  
  
 <span data-ttu-id="8e0a2-118">这将指定绑定到顶级 UI 元素的数据也绑定到此控件（即唱片集数组）。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-118">This specifies that the data bound to the top-level UI element is also bound to this control (that is, the array of Albums).</span></span> <span data-ttu-id="8e0a2-119">此外，`ItemTemplate="{StaticResource AlbumStyle}"` 指定将用于 `ListBox` 中每个项的数据模板。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-119">In addition, `ItemTemplate="{StaticResource AlbumStyle}"` specifies the data template to be used for each item in the `ListBox`.</span></span> <span data-ttu-id="8e0a2-120">您也可以定义数据模板以指定应如何格式化数据。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-120">You can also define data templates to specify how the data should be formatted.</span></span> <span data-ttu-id="8e0a2-121">应用程序中的其他 UI 元素可以重复使用这些数据模板，优点是在同一位置定义和维护数据模板。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-121">These data templates can be reused for other UI elements in the application, the advantage is that the data template is defined and maintained in one place.</span></span>  
  
 <span data-ttu-id="8e0a2-122">`AlbumStyle` 数据模板并排使用两个 `TextBlock` 布置网格。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-122">The `AlbumStyle` data template lays out a grid with two `TextBlock`s side by side.</span></span> <span data-ttu-id="8e0a2-123">一个指定唱片集的名称，另一个指定唱片集中的曲目数。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-123">One specifies the name of the Album and the other the number of Tracks in the album.</span></span>  
  
```xaml  
<DataTemplate x:Key="AlbumStyle">  
    <Grid>  
        <Grid.ColumnDefinitions>  
            <ColumnDefinition Width="260" />  
            <ColumnDefinition Width="60" />  
        </Grid.ColumnDefinitions>  
        <TextBlock Grid.Column="0" TextContent="{Binding Path=Title}" />  
        <TextBlock Grid.Column="1" TextContent="{Binding Path=Tracks#.Count}" HorizontalAlignment="Right" />  
    </Grid>  
</DataTemplate>  
```  
  
 <span data-ttu-id="8e0a2-124">下面的 XAML 代码创建另一个 `ListBox`。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-124">The following XAML code creates a second `ListBox`.</span></span>  
  
```xaml  
<ListBox Grid.Row="2"   
            Grid.ColumnSpan="2"   
            ItemTemplate="{StaticResource TrackStyle}"  
            ItemsSource="{Binding Path=Tracks}" />  
```  
  
 <span data-ttu-id="8e0a2-125">该代码指定 `ItemsSource` 的路径。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-125">The code specifies a path for the `ItemsSource`.</span></span> <span data-ttu-id="8e0a2-126">这表示绑定到此控件的数据不是顶级数据，而是名为 `Tracks` 的顶级数据的属性。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-126">This indicates that the data bound to this control is not the top-level data but a property of the top-level data named `Tracks`.</span></span> <span data-ttu-id="8e0a2-127">此属性表示唱片集内包含的曲目数组。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-127">This property represents the array of tracks contained within the album.</span></span> <span data-ttu-id="8e0a2-128">此外，指定了名为 `DataTemplate` 的另一个 `TrackStyle`。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-128">In addition, a different `DataTemplate` named `TrackStyle` is specified.</span></span> <span data-ttu-id="8e0a2-129">`TrackStyle` 模板的布局类似于 `AlbumStyle` 模板的布局，但 `TextBlock` 绑定到不同的属性。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-129">The layout of the `TrackStyle` template is similar to that of the `AlbumStyle` template, but the `TextBlock`s are bound to different properties.</span></span> <span data-ttu-id="8e0a2-130">这是因为两个模板用于不同的数据对象。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-130">This is because the two templates are used with different data objects.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8e0a2-131">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="8e0a2-131">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8e0a2-132">确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-132">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="8e0a2-133">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="8e0a2-134">若要在单或跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8e0a2-135">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-135">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8e0a2-136">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="8e0a2-136">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8e0a2-137">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="8e0a2-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8e0a2-138">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="8e0a2-138">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WPFDataBinding`  
  
## <a name="see-also"></a><span data-ttu-id="8e0a2-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e0a2-139">See Also</span></span>
