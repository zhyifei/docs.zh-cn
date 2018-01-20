---
title: "具有 ASP.NET 的 LINQ to SQL N 层"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f6cc863a-d6a6-4281-ba8b-197c01cf6c6f
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 5069c518998ca1d93f6e1ce94d76c8d0c7da07bd
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="linq-to-sql-n-tier-with-aspnet"></a><span data-ttu-id="7398d-102">具有 ASP.NET 的 LINQ to SQL N 层</span><span class="sxs-lookup"><span data-stu-id="7398d-102">LINQ to SQL N-Tier with ASP.NET</span></span>
<span data-ttu-id="7398d-103">在使用 [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] 的 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]应用程序中，可以使用 <xref:System.Web.UI.WebControls.LinqDataSource> Web 服务器控件。</span><span class="sxs-lookup"><span data-stu-id="7398d-103">In [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] applications that use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], you use the <xref:System.Web.UI.WebControls.LinqDataSource> Web server control.</span></span> <span data-ttu-id="7398d-104">此控件处理查询 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]时必须使用的大部分逻辑，将数据传递到浏览器，检索数据，并将数据提交给 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> ，然后由其更新数据库。</span><span class="sxs-lookup"><span data-stu-id="7398d-104">The control handles most of the logic that it must have to query against [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], pass the data to the browser, retrieve it, and submit it to the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> which then updates the database.</span></span> <span data-ttu-id="7398d-105">只需要在标记中配置该控件，然后由该控件处理 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 和浏览器之间的所有数据传输。</span><span class="sxs-lookup"><span data-stu-id="7398d-105">You just configure the control in the markup, and the control handles all the data transfer between [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] and the browser.</span></span> <span data-ttu-id="7398d-106">由于该控件处理与表示层之间的交互， [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 处理与数据层之间的通信，因此对于 [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] 多层应用程序，您的主要重点是编写自定义业务逻辑。</span><span class="sxs-lookup"><span data-stu-id="7398d-106">Because the control handles the interactions with the presentation tier, and [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] handles the communication with the data tier, your main focus in [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] multitier applications is on writing your custom business logic.</span></span>  
  
 <span data-ttu-id="7398d-107">有关详细信息`LINQDataSource`，请参阅[NIB: LinqDataSource Web 服务器控件概述](http://msdn.microsoft.com/library/104cfc3f-7385-47d3-8a51-830dfa791136)。</span><span class="sxs-lookup"><span data-stu-id="7398d-107">For more information about `LINQDataSource`, see [NIB: LinqDataSource Web Server Control Overview](http://msdn.microsoft.com/library/104cfc3f-7385-47d3-8a51-830dfa791136).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7398d-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="7398d-108">See Also</span></span>  
 [<span data-ttu-id="7398d-109">使用 LINQ to SQL 的 N 层和远程应用程序</span><span class="sxs-lookup"><span data-stu-id="7398d-109">N-Tier and Remote Applications with LINQ to SQL</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)
