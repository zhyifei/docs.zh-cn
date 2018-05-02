---
title: 在 Visual Basic 应用程序中访问数据
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- data [Visual Basic]
- Visual Basic, data access
ms.assetid: 3086ab38-3be5-4b22-9385-7d0e16b04f6a
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 306a618f193f9223443938ae2a9e0996c1b5295c
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="accessing-data-in-visual-basic-applications"></a><span data-ttu-id="f9de1-102">在 Visual Basic 应用程序中访问数据</span><span class="sxs-lookup"><span data-stu-id="f9de1-102">Accessing data in Visual Basic applications</span></span>
<span data-ttu-id="f9de1-103">Visual Basic 包括多种新功能，以帮助开发访问数据的应用程序。</span><span class="sxs-lookup"><span data-stu-id="f9de1-103">Visual Basic includes several new features to assist in developing applications that access data.</span></span> <span data-ttu-id="f9de1-104">通过将项从[“数据源”窗口](/visualstudio/data-tools/add-new-data-sources)拖到窗体上来创建 Windows 应用程序的数据绑定窗体。</span><span class="sxs-lookup"><span data-stu-id="f9de1-104">Data-bound forms for Windows applications are created by dragging items from the [Data Sources Window](/visualstudio/data-tools/add-new-data-sources) onto the form.</span></span> <span data-ttu-id="f9de1-105">通过将项从“数据源窗口”拖动到现有控件上来将控件绑定到数据。</span><span class="sxs-lookup"><span data-stu-id="f9de1-105">You bind controls to data by dragging items from the **Data Sources Window** onto existing controls.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f9de1-106">相关章节</span><span class="sxs-lookup"><span data-stu-id="f9de1-106">Related sections</span></span>  
 [<span data-ttu-id="f9de1-107">在 Visual Studio 中访问数据</span><span class="sxs-lookup"><span data-stu-id="f9de1-107">Accessing Data in Visual Studio</span></span>](/visualstudio/data-tools/)  
 <span data-ttu-id="f9de1-108">提供相关页面链接，这些页面讨论如何将数据访问功能结合到应用程序中。</span><span class="sxs-lookup"><span data-stu-id="f9de1-108">Provides links to pages that discuss incorporating data access functionality into your applications.</span></span>

 [<span data-ttu-id="f9de1-109">适用于 NET 的 Visual Studio Data Tools</span><span class="sxs-lookup"><span data-stu-id="f9de1-109">Visual Studio data tools for .NET</span></span>](/visualstudio/data-tools/visual-studio-data-tools-for-dotnet)  
 <span data-ttu-id="f9de1-110">提供相关页面链接，这些页面介绍如何使用 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] 创建处理数据的应用程序。</span><span class="sxs-lookup"><span data-stu-id="f9de1-110">Provides links to pages on creating applications that work with data, using [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span></span>  
  
 [<span data-ttu-id="f9de1-111">LINQ</span><span class="sxs-lookup"><span data-stu-id="f9de1-111">LINQ</span></span>](../../visual-basic/programming-guide/language-features/linq/index.md)  
 <span data-ttu-id="f9de1-112">提供介绍如何在 Visual Basic 中使用 LINQ 的主题的链接。</span><span class="sxs-lookup"><span data-stu-id="f9de1-112">Provides links to topics that describe how to use LINQ with Visual Basic.</span></span>  
  
 [<span data-ttu-id="f9de1-113">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="f9de1-113">LINQ to SQL</span></span>](../../framework/data/adonet/sql/linq/index.md)  
 <span data-ttu-id="f9de1-114">提供有关 [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] 的信息。</span><span class="sxs-lookup"><span data-stu-id="f9de1-114">Provides information about [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="f9de1-115">包括编程示例。</span><span class="sxs-lookup"><span data-stu-id="f9de1-115">Includes programming examples.</span></span>  
  
 [<span data-ttu-id="f9de1-116">Visual Studio 中的 LINQ to SQL 工具</span><span class="sxs-lookup"><span data-stu-id="f9de1-116">LINQ to SQL Tools in Visual Studio</span></span>](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)  
 <span data-ttu-id="f9de1-117">提供介绍如何在应用程序中创建 [LINQ to SQL](../../framework/data/adonet/sql/linq/index.md) 对象模型的主题的链接。</span><span class="sxs-lookup"><span data-stu-id="f9de1-117">Provides links to topics about how to create a [LINQ to SQL](../../framework/data/adonet/sql/linq/index.md) object model in applications.</span></span>  
  
 [<span data-ttu-id="f9de1-118">在 N 层应用程序中使用数据集</span><span class="sxs-lookup"><span data-stu-id="f9de1-118">Work with datasets in n-tier applications</span></span>](/visualstudio/data-tools/work-with-datasets-in-n-tier-applications)  
 <span data-ttu-id="f9de1-119">提供介绍如何创建多层数据应用程序的主题的链接。</span><span class="sxs-lookup"><span data-stu-id="f9de1-119">Provides links to topics about how to create multitiered data applications.</span></span>  
     
 [<span data-ttu-id="f9de1-120">添加新连接</span><span class="sxs-lookup"><span data-stu-id="f9de1-120">Add new connections</span></span>](/visualstudio/data-tools/add-new-connections)  
 <span data-ttu-id="f9de1-121">提供相关页面的链接，这些页面介绍如何通过 [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] 使用设计时工具和 ADO.NET 连接对象将应用程序连接到数据。</span><span class="sxs-lookup"><span data-stu-id="f9de1-121">Provides links to pages on connecting your application to data with design-time tools and ADO.NET connection objects, using [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].</span></span>  

 [<span data-ttu-id="f9de1-122">Visual Studio 中的数据集工具</span><span class="sxs-lookup"><span data-stu-id="f9de1-122">Dataset Tools in Visual Studio</span></span>](/visualstudio/data-tools/dataset-tools-in-visual-studio)  
 <span data-ttu-id="f9de1-123">提供介绍如何将数据加载到数据集以及如何执行 SQL 语句和存储过程的页面的链接。</span><span class="sxs-lookup"><span data-stu-id="f9de1-123">Provides links to pages describing how to load data into datasets and how to execute SQL statements and stored procedures.</span></span>  
  
 [<span data-ttu-id="f9de1-124">在 Visual Studio 中将控件绑定到数据</span><span class="sxs-lookup"><span data-stu-id="f9de1-124">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)  
 <span data-ttu-id="f9de1-125">提供说明如何通过数据绑定控件在 Windows 窗体上显示数据的页面的链接。</span><span class="sxs-lookup"><span data-stu-id="f9de1-125">Provides links to pages that explain how to display data on Windows Forms through data-bound controls.</span></span>  
  
 [<span data-ttu-id="f9de1-126">编辑数据集中的数据</span><span class="sxs-lookup"><span data-stu-id="f9de1-126">Edit Data in Datasets</span></span>](/visualstudio/data-tools/edit-data-in-datasets)  
 <span data-ttu-id="f9de1-127">提供介绍如何操作数据集的数据表中数据的页面的链接。</span><span class="sxs-lookup"><span data-stu-id="f9de1-127">Provides links to pages describing how to manipulate the data in the data tables of a dataset.</span></span>  
  
 [<span data-ttu-id="f9de1-128">验证数据集中的数据</span><span class="sxs-lookup"><span data-stu-id="f9de1-128">Validate data in datasets</span></span>](/visualstudio/data-tools/validate-data-in-datasets)  
 <span data-ttu-id="f9de1-129">提供介绍如何在列和行更改过程中向数据集添加验证的页面的链接。</span><span class="sxs-lookup"><span data-stu-id="f9de1-129">Provides links to pages describing how to add validation to a dataset during column and row changes.</span></span>  
  
 [<span data-ttu-id="f9de1-130">将数据保存回数据库</span><span class="sxs-lookup"><span data-stu-id="f9de1-130">Save data back to the database</span></span>](/visualstudio/data-tools/save-data-back-to-the-database)  
 <span data-ttu-id="f9de1-131">提供说明如何将更新后的数据从应用程序发送到数据库的页面的链接。</span><span class="sxs-lookup"><span data-stu-id="f9de1-131">Provides links to pages explaining how to send updated data from an application to the database.</span></span>  
  
 [<span data-ttu-id="f9de1-132">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="f9de1-132">ADO.NET</span></span>](../../framework/data/adonet/index.md)  
 <span data-ttu-id="f9de1-133">描述 ADO.NET 类，该类向 .NET Framework 程序员公开数据访问服务。</span><span class="sxs-lookup"><span data-stu-id="f9de1-133">Describes the ADO.NET classes, which expose data-access services to the .NET Framework programmer.</span></span>

 [<span data-ttu-id="f9de1-134">Office 解决方案中的数据</span><span class="sxs-lookup"><span data-stu-id="f9de1-134">Data in Office Solutions</span></span>](https://msdn.microsoft.com/library/xx069ybh)  
 <span data-ttu-id="f9de1-135">包含相关页面的链接，这些页面阐释了数据在 Office 解决方案中的工作方式（包括有关面向架构的编程、数据缓存和服务器端数据访问的信息）。</span><span class="sxs-lookup"><span data-stu-id="f9de1-135">Contains links to pages that explain how data works in Office solutions, including information about schema-oriented programming, data caching, and server-side data access.</span></span>
