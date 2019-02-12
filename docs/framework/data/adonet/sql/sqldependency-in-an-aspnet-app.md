---
title: ASP.NET 应用程序中的 SqlDependency
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ff226ce3-f6b5-47a1-8d22-dc78b67e07f5
ms.openlocfilehash: 42eb0a417659776b2cd2fffa9d2fd62e58a4a176
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2019
ms.locfileid: "56091976"
---
# <a name="sqldependency-in-an-aspnet-application"></a><span data-ttu-id="ad0f6-102">ASP.NET 应用程序中的 SqlDependency</span><span class="sxs-lookup"><span data-stu-id="ad0f6-102">SqlDependency in an ASP.NET Application</span></span>
<span data-ttu-id="ad0f6-103">本节中的示例演示如果通过利用 ASP.NET <xref:System.Data.SqlClient.SqlDependency> 对象间接使用 <xref:System.Web.Caching.SqlCacheDependency>。</span><span class="sxs-lookup"><span data-stu-id="ad0f6-103">The example in this section shows how to use <xref:System.Data.SqlClient.SqlDependency> indirectly by leveraging the ASP.NET <xref:System.Web.Caching.SqlCacheDependency> object.</span></span> <span data-ttu-id="ad0f6-104">
  <xref:System.Web.Caching.SqlCacheDependency> 对象使用 <xref:System.Data.SqlClient.SqlDependency> 来侦听通知和正确更新缓存。</span><span class="sxs-lookup"><span data-stu-id="ad0f6-104">The <xref:System.Web.Caching.SqlCacheDependency> object uses a <xref:System.Data.SqlClient.SqlDependency> to listen for notifications and correctly update the cache.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad0f6-105">示例代码假定你已通过执行中的脚本启用查询通知[启用查询通知](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="ad0f6-105">The sample code assumes that you have enabled query notifications by executing the scripts in [Enabling Query Notifications](../../../../../docs/framework/data/adonet/sql/enabling-query-notifications.md).</span></span>  
  
## <a name="about-the-sample-application"></a><span data-ttu-id="ad0f6-106">关于示例应用程序</span><span class="sxs-lookup"><span data-stu-id="ad0f6-106">About the Sample Application</span></span>  
 <span data-ttu-id="ad0f6-107">示例应用程序使用单个 ASP.NET 网页来显示产品信息从**AdventureWorks**中的 SQL Server 数据库<xref:System.Web.UI.WebControls.GridView>控件。</span><span class="sxs-lookup"><span data-stu-id="ad0f6-107">The sample application uses a single ASP.NET Web page to display product information from the **AdventureWorks** SQL Server database in a <xref:System.Web.UI.WebControls.GridView> control.</span></span> <span data-ttu-id="ad0f6-108">加载页面时，代码将当前时间写入 <xref:System.Web.UI.WebControls.Label> 控件。</span><span class="sxs-lookup"><span data-stu-id="ad0f6-108">When the page loads, the code writes the current time to a <xref:System.Web.UI.WebControls.Label> control.</span></span> <span data-ttu-id="ad0f6-109">然后，它定义一个 <xref:System.Web.Caching.SqlCacheDependency> 对象并设置 <xref:System.Web.Caching.Cache> 对象的属性，以存储最多三分钟的缓存数据。</span><span class="sxs-lookup"><span data-stu-id="ad0f6-109">It then defines a <xref:System.Web.Caching.SqlCacheDependency> object and sets properties on the <xref:System.Web.Caching.Cache> object to store the cache data for up to three minutes.</span></span> <span data-ttu-id="ad0f6-110">然后，代码连接到数据库并检索数据。</span><span class="sxs-lookup"><span data-stu-id="ad0f6-110">The code then connects to the database and retrieves the data.</span></span> <span data-ttu-id="ad0f6-111">加载页面后且应用程序运行时，ASP.NET 将从缓存中检索数据，这可以通过观察页面上的时间不改变来加以验证。</span><span class="sxs-lookup"><span data-stu-id="ad0f6-111">When the page is loaded and the application is running ASP.NET will retrieve data from the cache, which you can verify by noting that the time on the page does not change.</span></span> <span data-ttu-id="ad0f6-112">如果监视的数据发生更改，ASP.NET 将令缓存失效并用新数据重新填充 `GridView` 控件，更新 `Label` 控件中显示的时间。</span><span class="sxs-lookup"><span data-stu-id="ad0f6-112">If the data being monitored changes, ASP.NET invalidates the cache and repopulate the `GridView` control with fresh data, updating the time displayed in the `Label` control.</span></span>  
  
## <a name="creating-the-sample-application"></a><span data-ttu-id="ad0f6-113">创建示例应用程序</span><span class="sxs-lookup"><span data-stu-id="ad0f6-113">Creating the Sample Application</span></span>  
 <span data-ttu-id="ad0f6-114">请执行下面的步骤来创建并运行示例应用程序：</span><span class="sxs-lookup"><span data-stu-id="ad0f6-114">Follow these steps to create and run the sample application:</span></span>  
  
1.  <span data-ttu-id="ad0f6-115">创建一个新的 ASP.NET 网站。</span><span class="sxs-lookup"><span data-stu-id="ad0f6-115">Create a new ASP.NET Web site.</span></span>  
  
2.  <span data-ttu-id="ad0f6-116">向 Default.aspx 页面添加一个 <xref:System.Web.UI.WebControls.Label> 和一个 <xref:System.Web.UI.WebControls.GridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="ad0f6-116">Add a <xref:System.Web.UI.WebControls.Label> and a <xref:System.Web.UI.WebControls.GridView> control to the Default.aspx page.</span></span>  
  
3.  <span data-ttu-id="ad0f6-117">打开该页面的类模块并添加下面的指令：</span><span class="sxs-lookup"><span data-stu-id="ad0f6-117">Open the page's class module and add the following directives:</span></span>  
  
    ```vb  
    Option Strict On  
    Option Explicit On  
  
    Imports System.Data.SqlClient  
    ```  
  
    ```csharp  
    using System.Data.SqlClient;  
    using System.Web.Caching;  
    ```  
  
4.  <span data-ttu-id="ad0f6-118">在该页面的 `Page_Load` 事件中添加下面的代码：</span><span class="sxs-lookup"><span data-stu-id="ad0f6-118">Add the following code in the page's `Page_Load` event:</span></span>  
  
     [!code-csharp[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#1)]
     [!code-vb[DataWorks SqlDependency.AspNet#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#1)]  
  
5.  <span data-ttu-id="ad0f6-119">添加两个帮助器方法 `GetConnectionString` 和 `GetSQL`。</span><span class="sxs-lookup"><span data-stu-id="ad0f6-119">Add two helper methods, `GetConnectionString` and `GetSQL`.</span></span> <span data-ttu-id="ad0f6-120">已定义的连接字符串使用集成安全性。</span><span class="sxs-lookup"><span data-stu-id="ad0f6-120">The connection string defined uses integrated security.</span></span> <span data-ttu-id="ad0f6-121">将需要验证所使用的帐户具有必要的数据库权限，并且示例数据库**AdventureWorks**，是否启用了通知。</span><span class="sxs-lookup"><span data-stu-id="ad0f6-121">You will need to verify that the account you are using has the necessary database permissions and that the sample database, **AdventureWorks**, has notifications enabled.</span></span>
  
     [!code-csharp[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/CS/Default.aspx.cs#2)]
     [!code-vb[DataWorks SqlDependency.AspNet#2](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlDependency.AspNet/VB/Default.aspx.vb#2)]  
  
### <a name="testing-the-application"></a><span data-ttu-id="ad0f6-122">测试应用程序</span><span class="sxs-lookup"><span data-stu-id="ad0f6-122">Testing the Application</span></span>  
 <span data-ttu-id="ad0f6-123">如果没有活动，应用程序将会缓存 Web 窗体上显示的数据并每隔三分钟刷新一次。</span><span class="sxs-lookup"><span data-stu-id="ad0f6-123">The application caches the data displayed on the Web form and refreshes it every three minutes if there is no activity.</span></span> <span data-ttu-id="ad0f6-124">如果对数据库发生了更改，则立即刷新缓存。</span><span class="sxs-lookup"><span data-stu-id="ad0f6-124">If a change occurs to the database, the cache is refreshed immediately.</span></span> <span data-ttu-id="ad0f6-125">从 Visual Studio 中运行应用程序，将页面加载到浏览器中。</span><span class="sxs-lookup"><span data-stu-id="ad0f6-125">Run the application from Visual Studio, which loads the page into the browser.</span></span> <span data-ttu-id="ad0f6-126">显示的缓存刷新时间指示最后刷新缓存的时间。</span><span class="sxs-lookup"><span data-stu-id="ad0f6-126">The cache refresh time displayed indicates when the cache was last refreshed.</span></span> <span data-ttu-id="ad0f6-127">等待三分钟，然后刷新页面，使回发事件发生。</span><span class="sxs-lookup"><span data-stu-id="ad0f6-127">Wait three minutes, and then refresh the page, causing a postback event to occur.</span></span> <span data-ttu-id="ad0f6-128">请注意，页面上显示的时间已发生改变。</span><span class="sxs-lookup"><span data-stu-id="ad0f6-128">Note that the time displayed on the page has changed.</span></span> <span data-ttu-id="ad0f6-129">如果您在三分钟之内刷新页面，页面上显示的时间将保持不变。</span><span class="sxs-lookup"><span data-stu-id="ad0f6-129">If you refresh the page in less than three minutes, the time displayed on the page will remain the same.</span></span>  
  
 <span data-ttu-id="ad0f6-130">现在使用 Transact-SQL UPDATE 命令更新数据库中的数据并刷新页面。</span><span class="sxs-lookup"><span data-stu-id="ad0f6-130">Now update the data in the database, using a Transact-SQL UPDATE command and refresh the page.</span></span> <span data-ttu-id="ad0f6-131">此时显示的时间指示已用数据库中的新数据刷新了缓存。</span><span class="sxs-lookup"><span data-stu-id="ad0f6-131">The time displayed now indicates that the cache was refreshed with the new data from the database.</span></span> <span data-ttu-id="ad0f6-132">请注意，虽然已更新缓存，但页面上显示的时间在回发事件发生之前仍将保持不变。</span><span class="sxs-lookup"><span data-stu-id="ad0f6-132">Note that although the cache is updated, the time displayed on the page does not change until a postback event occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad0f6-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad0f6-133">See also</span></span>
- [<span data-ttu-id="ad0f6-134">SQL Server 中的查询通知</span><span class="sxs-lookup"><span data-stu-id="ad0f6-134">Query Notifications in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/query-notifications-in-sql-server.md)
- [<span data-ttu-id="ad0f6-135">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="ad0f6-135">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
