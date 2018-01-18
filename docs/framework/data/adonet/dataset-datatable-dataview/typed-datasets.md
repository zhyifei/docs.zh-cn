---
title: "类型化数据集"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: a68d4a10b01285a7e1b33238409351ca04d0aeb4
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="typed-datasets"></a><span data-ttu-id="469e5-102">类型化数据集</span><span class="sxs-lookup"><span data-stu-id="469e5-102">Typed DataSets</span></span>
<span data-ttu-id="469e5-103">在允许通过弱类型化变量对值进行后期绑定访问的同时，<xref:System.Data.DataSet> 还允许通过强类型化比喻对数据进行访问。</span><span class="sxs-lookup"><span data-stu-id="469e5-103">Along with late bound access to values through weakly typed variables, the <xref:System.Data.DataSet> provides access to data through a strongly typed metaphor.</span></span> <span data-ttu-id="469e5-104">表和列属于**数据集**可以使用用户友好名称来访问和强类型化变量。</span><span class="sxs-lookup"><span data-stu-id="469e5-104">Tables and columns that are part of the **DataSet** can be accessed using user-friendly names and strongly typed variables.</span></span>  
  
 <span data-ttu-id="469e5-105">类型化**数据集**是派生自的类**数据集**。</span><span class="sxs-lookup"><span data-stu-id="469e5-105">A typed **DataSet** is a class that derives from a **DataSet**.</span></span> <span data-ttu-id="469e5-106">在这种情况下，它继承所有方法、 事件和属性的**数据集**。</span><span class="sxs-lookup"><span data-stu-id="469e5-106">As such, it inherits all the methods, events, and properties of a **DataSet**.</span></span> <span data-ttu-id="469e5-107">此外，类型化**数据集**提供强类型化的方法、 事件和属性。</span><span class="sxs-lookup"><span data-stu-id="469e5-107">Additionally, a typed **DataSet** provides strongly typed methods, events, and properties.</span></span> <span data-ttu-id="469e5-108">这意味着可以按名称（而不是使用基于集合的方法）访问表和列。</span><span class="sxs-lookup"><span data-stu-id="469e5-108">This means you can access tables and columns by name, instead of using collection-based methods.</span></span> <span data-ttu-id="469e5-109">除了提高代码，类型化的可读性之外**数据集**还允许 Visual Studio.NET 代码编辑器自动填写您键入的行。</span><span class="sxs-lookup"><span data-stu-id="469e5-109">Aside from the improved readability of the code, a typed **DataSet** also allows the Visual Studio .NET code editor to automatically complete lines as you type.</span></span>  
  
 <span data-ttu-id="469e5-110">此外，强类型**数据集**在编译时提供正确的类型为值的访问。</span><span class="sxs-lookup"><span data-stu-id="469e5-110">Additionally, the strongly typed **DataSet** provides access to values as the correct type at compile time.</span></span> <span data-ttu-id="469e5-111">通过强类型化**数据集**，代码时编译而不是在运行时捕获类型不匹配错误。</span><span class="sxs-lookup"><span data-stu-id="469e5-111">With a strongly typed **DataSet**, type mismatch errors are caught when the code is compiled rather than at run time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="469e5-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="469e5-112">In This Section</span></span>  
 [<span data-ttu-id="469e5-113">生成强类型化数据集</span><span class="sxs-lookup"><span data-stu-id="469e5-113">Generating Strongly Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-strongly-typed-datasets.md)  
 <span data-ttu-id="469e5-114">描述如何创建和使用强类型化**数据集**。</span><span class="sxs-lookup"><span data-stu-id="469e5-114">Describes how to create and use a strongly typed **DataSet**.</span></span>  
  
 [<span data-ttu-id="469e5-115">为类型化的数据集进行注释</span><span class="sxs-lookup"><span data-stu-id="469e5-115">Annotating Typed DataSets</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/annotating-typed-datasets.md)  
 <span data-ttu-id="469e5-116">描述如何批注 XML 架构定义语言 (XSD) 架构用于生成强类型化**数据集**，使**数据集**元素友好的名称，而无需更改基础架构。</span><span class="sxs-lookup"><span data-stu-id="469e5-116">Describes how to annotate the XML Schema definition language (XSD) schema used to generate a strongly typed **DataSet**, to give **DataSet** elements friendly names without altering the underlying schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="469e5-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="469e5-117">See Also</span></span>  
 [<span data-ttu-id="469e5-118">数据集、数据表和数据视图</span><span class="sxs-lookup"><span data-stu-id="469e5-118">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [<span data-ttu-id="469e5-119">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="469e5-119">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
