---
title: 演练：在 WPF 应用程序中缓存应用程序数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthroughs [WPF], caching
- caching [.NET Framework]
- caching [WPF]
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
ms.openlocfilehash: 7a4f84281da78068b5c6f7a505c8cb9225b31a39
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33548894"
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a>演练：在 WPF 应用程序中缓存应用程序数据
缓存可以将数据存储在内存中以便快速访问。 当再次访问数据时，应用程序可以从改为从原始源检索该缓存获取数据。 这可改善性能和可伸缩性。 此外，数据源暂时不可用时，缓存可提供数据。  
  
 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]提供使你可以使用中的缓存类[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]应用程序。 这些类位于<xref:System.Runtime.Caching>命名空间。  
  
> [!NOTE]
>  <xref:System.Runtime.Caching>命名空间是中的新增功能[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。 此命名空间使缓存可供所有[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]应用程序。 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 以前的版本中，缓存仅在 <xref:System.Web> 命名空间可用，因此，需要 ASP.NET 类上的一个依赖项。  
  
 本演练演示如何使用中提供的缓存功能[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]作为的一部分[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]应用程序。 在本演练中，你将缓存的文本文件的内容。  
  
 本演练演示以下任务：  
  
-   创建 WPF 应用程序项目。  
  
-   添加对引用[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。  
  
-   正在初始化缓存。  
  
-   添加包含的文本文件的内容的缓存项。  
  
-   提供的缓存项的逐出策略。  
  
-   监视缓存的文件的路径和有关通知的缓存实例更改为受监视的项目。  
  
## <a name="prerequisites"></a>系统必备  
 若要完成本演练，你将需要：  
  
-   Microsoft [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]。  
  
-   包含文本的少量的文本文件。 （将文本文件的内容在显示一个消息框。）在本演练中所示的代码假定你正在与以下文件：  
  
     `c:\cache\cacheText.txt`  
  
     但是，你可以使用任何文本文件并对此演练中的代码进行少量更改。  
  
## <a name="creating-a-wpf-application-project"></a>创建 WPF 应用程序项目  
 首先创建一个 WPF 应用程序项目。  
  
#### <a name="to-create-a-wpf-application"></a>创建 WPF 应用程序  
  
1.  启动 Visual Studio。  
  
2.  在**文件**菜单上，单击**新建**，然后单击**新项目**。  
  
     随即显示“新建项目”对话框。  
  
3.  下**已安装的模板**，选择你想要使用的编程语言 (**Visual Basic**或**Visual C#**)。  
  
4.  在**新项目**对话框中，选择**WPF 应用程序**。  
  
    > [!NOTE]
    >  如果看不到**WPF 应用程序**模板，请确保你面向的版本[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]支持 WPF。 在**新项目**对话框中，选择[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]从列表中。  
  
5.  在**名称**文本框中，输入你的项目的名称。 例如，你可以输入**WPFCaching**。  
  
6.  选择**创建解决方案的目录**复选框。  
  
7.  单击 **“确定”**。  
  
     WPF 设计器中打开**设计**查看，并显示 MainWindow.xaml 文件。 Visual Studio 将创建**我的项目**文件夹、 Application.xaml 文件和 MainWindow.xaml 文件。  
  
## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a>面向.NET Framework 和添加对缓存程序集的引用  
 默认情况下，WPF 应用程序目标[!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]。 若要使用<xref:System.Runtime.Caching>在 WPF 应用程序的命名空间，应用程序必须指定目标[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (不[!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) 并且必须包括对命名空间的引用。  
  
 因此下, 一步是以更改.NET Framework 目标并添加对的引用<xref:System.Runtime.Caching>命名空间。  
  
> [!NOTE]
>  .NET Framework 将目标更改的过程是在 Visual Basic 项目和 Visual C# 项目不同。  
  
#### <a name="to-change-the-target-net-framework-in-visual-basic"></a>若要更改的目标.NET Framework 在 Visual Basic 中  
  
1.  在**解决方案资源管理器**，右键单击项目名称，然后单击**属性**。  
  
     应用程序的属性窗口将显示。  
  
2.  单击“编译”选项卡。  
  
3.  在窗口的底部，单击**高级编译选项...**.  
  
     **高级编译器设置**对话框随即显示。  
  
4.  在**目标 framework （所有配置）** 列表中，选择[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。 (不要选择[!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]。)  
  
5.  单击 **“确定”**。  
  
     **目标 Framework 更改**对话框随即显示。  
  
6.  在**目标 Framework 更改**对话框中，单击**是**。  
  
     项目将关闭，然后重新打开。  
  
7.  通过执行以下步骤添加对缓存程序集的引用：  
  
    1.  在**解决方案资源管理器**，右键单击项目的名称，然后单击**添加引用**。  
  
    2.  选择 **.NET**选项卡上，选择`System.Runtime.Caching`，然后单击**确定**。  
  
#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a>若要更改 Visual C# 项目中的目标.NET Framework  
  
1.  在**解决方案资源管理器**，右键单击项目名称，然后单击**属性**。  
  
     应用程序的属性窗口将显示。  
  
2.  单击“应用程序”  选项卡。  
  
3.  在**目标框架**列表中，选择[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。 (不要选择 **.NET Framework 4 Client Profile**。)  
  
4.  通过执行以下步骤添加对缓存程序集的引用：  
  
    1.  右键单击**引用**文件夹，然后单击**添加引用**。  
  
    2.  选择 **.NET**选项卡上，选择`System.Runtime.Caching`，然后单击**确定**。  
  
## <a name="adding-a-button-to-the-wpf-window"></a>将按钮添加到作为 WPF 窗口  
 接下来，你将添加一个按钮控件，并创建为按钮的事件处理程序`Click`事件。 稍后你将添加到的代码，因此单击按钮时，文本文件的内容是缓存，并且不显示。  
  
#### <a name="to-add-a-button-control"></a>若要添加一个按钮控件  
  
1.  在**解决方案资源管理器**，双击 MainWindow.xaml 文件，以打开它。  
  
2.  从**工具箱**下**公共 WPF 控件**，拖动`Button`控制转移到`MainWindow`窗口。  
  
3.  在**属性**窗口中，设置`Content`属性`Button`控制转移到**获取缓存**。  
  
## <a name="initializing-the-cache-and-caching-an-entry"></a>正在初始化缓存和缓存条目  
 接下来，你将添加代码以执行以下任务：  
  
-   创建缓存类的实例 — 也就是说，你将实例化一个新<xref:System.Runtime.Caching.MemoryCache>对象。  
  
-   指定缓存使用<xref:System.Runtime.Caching.HostFileChangeMonitor>对象来监视的文本文件中的更改。  
  
-   读取文本文件，以及为缓存条目缓存其内容。  
  
-   显示缓存的文本文件的内容。  
  
#### <a name="to-create-the-cache-object"></a>若要创建缓存对象  
  
1.  双击你只是为了在 MainWindow.xaml.cs 或 MainWindow.Xaml.vb 文件创建一个事件处理程序添加的按钮。  
  
2.  在该文件 （后再类声明中） 的顶部，添加以下`Imports`(Visual Basic 中) 或`using`(C#) 语句：  
  
    ```csharp  
    using System.Runtime.Caching;  
    using System.IO;  
    ```  
  
    ```vb  
    Imports System.Runtime.Caching  
    Imports System.IO  
    ```  
  
3.  事件处理程序中，添加以下代码以实例化缓存对象：  
  
    ```csharp  
    ObjectCache cache = MemoryCache.Default;  
    ```  
  
    ```vb  
    Dim cache As ObjectCache = MemoryCache.Default  
    ```  
  
     <xref:System.Runtime.Caching.ObjectCache>类是一个内置的类，提供内存中对象缓存。  
  
4.  添加以下代码以读取名为某个缓存项的内容`filecontents`:  
  
    ```vb  
    Dim fileContents As String = TryCast(cache("filecontents"), String)  
    ```  
  
    ```csharp  
    string fileContents = cache["filecontents"] as string;  
    ```  
  
5.  添加以下代码以检查是否缓存条目名为`filecontents`存在：  
  
    ```vb  
    If fileContents Is Nothing Then  
  
    End If  
    ```  
  
    ```csharp  
    if (fileContents == null)  
    {  
  
    }  
    ```  
  
     如果指定的缓存条目不存在，必须读取该文本文件并将其作为某个缓存项添加到缓存。  
  
6.  在`if/then`块中，添加以下代码以创建一个新<xref:System.Runtime.Caching.CacheItemPolicy>对象，它指定的缓存项将在 10 秒后过期。  
  
    ```vb  
    Dim policy As New CacheItemPolicy()  
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)  
    ```  
  
    ```csharp  
    CacheItemPolicy policy = new CacheItemPolicy();  
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);  
    ```  
  
     如果未不提供任何逐出或过期的信息，则默认将<xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>，这意味着的缓存项永远不会基于仅在过期绝对时间。 相反，缓存条目过期只有在没有内存压力时。 作为最佳做法，应始终显式提供绝对或可调过期。  
  
7.  内部`if/then`块并在上一步中添加的代码，后面添加以下代码以创建你想要监视，并将该文本文件的路径添加到集合的文件路径的集合：  
  
    ```vb  
    Dim filePaths As New List(Of String)()  
    filePaths.Add("c:\cache\cacheText.txt")  
    ```  
  
    ```csharp  
    List<string> filePaths = new List<string>();  
    filePaths.Add("c:\\cache\\cacheText.txt");  
    ```  
  
    > [!NOTE]
    >  如果你想要使用的文本文件不是`c:\cache\cacheText.txt`，指定的文本文件是你想要使用的路径。  
  
8.  在上一步骤中，添加的代码后面添加以下代码以添加新<xref:System.Runtime.Caching.HostFileChangeMonitor>到的更改集合的对象的缓存项监视：  
  
    ```vb  
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))  
    ```  
  
    ```csharp  
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));  
    ```  
  
     <xref:System.Runtime.Caching.HostFileChangeMonitor>对象监视文本文件的路径，并通知缓存，如果未发生更改。 在此示例中，如果文件的内容发生更改，将过期的缓存项。  
  
9. 后面的代码中添加上一步中，添加以下代码以读取文本文件的内容：  
  
    ```vb  
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()  
    ```  
  
    ```csharp  
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + + "\n" + DateTime.Now;   
    ```  
  
     从而使你将能够看到该缓存条目到期时添加的日期和时间的时间戳。  
  
10. 在上一步骤中，添加的代码后面添加以下代码以将文件的内容插入到缓存对象作为<xref:System.Runtime.Caching.CacheItem>实例：  
  
    ```vb  
    cache.Set("filecontents", fileContents, policy)  
    ```  
  
    ```csharp  
    cache.Set("filecontents", fileContents, policy);  
    ```  
  
     指定有关如何通过传递逐出缓存项的信息<xref:System.Runtime.Caching.CacheItemPolicy>作为参数前面创建的对象。  
  
11. 后`if/then`块中，添加以下代码以在消息框中显示缓存的文件内容：  
  
    ```vb  
    MessageBox.Show(fileContents)  
    ```  
  
    ```csharp  
    MessageBox.Show(fileContents);  
    ```  
  
12. 在**生成**菜单上，单击**生成 WPFCaching**以生成项目。  
  
## <a name="testing-caching-in-the-wpf-application"></a>测试在 WPF 应用程序中缓存  
 你现在可以测试应用程序。  
  
#### <a name="to-test-caching-in-the-wpf-application"></a>若要测试缓存在 WPF 应用程序  
  
1.  按 Ctrl+F5 运行应用程序。  
  
     `MainWindow`显示窗口。  
  
2.  单击**获取缓存**。  
  
     在消息框中将显示文本文件中的缓存的内容。 请注意该文件上的时间戳。  
  
3.  关闭消息框，然后单击**获取缓存**再次 **。**  
  
     时间戳保持不变。 这将指示显示缓存的内容。  
  
4.  等待 10 秒或几秒，然后单击**获取缓存**试。  
  
     此时将显示新时间戳。 这表示策略，让过期的缓存项，将显示新的缓存的内容。  
  
5.  在文本编辑器中，打开您创建的文本文件。 不进行任何更改。  
  
6.  关闭消息框，然后单击**获取缓存**再次 **。**  
  
     再次注意时间戳。  
  
7.  对文本文件进行更改，然后保存该文件。  
  
8.  关闭消息框，然后单击**获取缓存**试。  
  
     此消息框包含从文本文件和新时间戳的更新的内容。 这指示主机文件更改监视器逐出缓存条目立即时更改的文件，即使绝对超时时间尚未过期。  
  
    > [!NOTE]
    >  你可以增加到 20 秒或更多以允许你进行更改，在文件中更多的时间的逐出时间。  
  
## <a name="code-example"></a>代码示例  
 完成本演练后，你创建的项目的代码将类似于下面的示例。  
  
 [!code-csharp[CachingWPFApplications#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Runtime.Caching.MemoryCache>  
 <xref:System.Runtime.Caching.ObjectCache>  
 <xref:System.Runtime.Caching>  
 [在 .NET Framework 应用程序中缓存](../../../../docs/framework/performance/caching-in-net-framework-applications.md)
