---
title: 具有 ASP.NET 的 LINQ to SQL N 层
ms.date: 03/30/2017
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
ms.openlocfilehash: 80c12d1c9f290657a6e005063d9cc77a17354abd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103723"
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a><span data-ttu-id="74253-102">具有 ASP.NET 的 LINQ to SQL N 层</span><span class="sxs-lookup"><span data-stu-id="74253-102">LINQ to SQL N-Tier with ASP.NET</span></span>
<span data-ttu-id="74253-103">在使用 [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] 的 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]应用程序中，可以使用 <xref:System.Web.UI.WebControls.LinqDataSource> Web 服务器控件。</span><span class="sxs-lookup"><span data-stu-id="74253-103">In [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] applications that use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you use the <xref:System.Web.UI.WebControls.LinqDataSource> Web server control.</span></span> <span data-ttu-id="74253-104">此控件处理查询 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]时必须使用的大部分逻辑，将数据传递到浏览器，检索数据，并将数据提交给 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> ，然后由其更新数据库。</span><span class="sxs-lookup"><span data-stu-id="74253-104">The control handles most of the logic that it must have to query against [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], pass the data to the browser, retrieve it, and submit it to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> which then updates the database.</span></span> <span data-ttu-id="74253-105">只需要在标记中配置该控件，然后由该控件处理 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 和浏览器之间的所有数据传输。</span><span class="sxs-lookup"><span data-stu-id="74253-105">You just configure the control in the markup, and the control handles all the data transfer between [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] and the browser.</span></span> <span data-ttu-id="74253-106">由于该控件处理与表示层之间的交互， [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 处理与数据层之间的通信，因此对于 [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] 多层应用程序，您的主要重点是编写自定义业务逻辑。</span><span class="sxs-lookup"><span data-stu-id="74253-106">Because the control handles the interactions with the presentation tier, and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] handles the communication with the data tier, your main focus in [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] multitier applications is on writing your custom business logic.</span></span>  
  
 <span data-ttu-id="74253-107">有关详细信息`LINQDataSource`，请参阅[LinqDataSource Web 服务器控件概述](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="74253-107">For more information about `LINQDataSource`, see [LinqDataSource Web Server Control Overview](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74253-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="74253-108">See also</span></span>

- [<span data-ttu-id="74253-109">使用 LINQ to SQL 的 N 层和远程应用程序</span><span class="sxs-lookup"><span data-stu-id="74253-109">N-Tier and Remote Applications with LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)
