---
title: "存储过程"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4d23dd7a-a85f-44ff-a717-af7d0950c0fc
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 7061fca911924de62cb522f4cf29481fb8cbeda7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="stored-procedures"></a><span data-ttu-id="d65c9-102">存储过程</span><span class="sxs-lookup"><span data-stu-id="d65c9-102">Stored Procedures</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="d65c9-103">在您的对象模型中使用方法来表示数据库中的存储的过程。</span><span class="sxs-lookup"><span data-stu-id="d65c9-103"> uses methods in your object model to represent stored procedures in the database.</span></span> <span data-ttu-id="d65c9-104">您可以通过应用 <xref:System.Data.Linq.Mapping.FunctionAttribute> 属性和 <xref:System.Data.Linq.Mapping.ParameterAttribute> 属性（如果需要）将方法指定为存储过程。</span><span class="sxs-lookup"><span data-stu-id="d65c9-104">You designate methods as stored procedures by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="d65c9-105">有关详细信息，请参阅[LINQ to SQL 对象模型](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)。</span><span class="sxs-lookup"><span data-stu-id="d65c9-105">For more information, see [The LINQ to SQL Object Model](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="d65c9-106">使用开发人员[!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]通常会使用[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]来映射存储的过程。</span><span class="sxs-lookup"><span data-stu-id="d65c9-106">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] would typically use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to map stored procedures.</span></span> <span data-ttu-id="d65c9-107">本节中的主题说明了在你自行编写代码的情况下，如何在你的应用程序中构建和调用这些方法。</span><span class="sxs-lookup"><span data-stu-id="d65c9-107">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d65c9-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="d65c9-108">In This Section</span></span>  
 [<span data-ttu-id="d65c9-109">如何：返回行集</span><span class="sxs-lookup"><span data-stu-id="d65c9-109">How to: Return Rowsets</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md)  
 <span data-ttu-id="d65c9-110">介绍如何返回数据行并说明如何使用输入参数。</span><span class="sxs-lookup"><span data-stu-id="d65c9-110">Describes how to return rows of data and shows how to use an input parameter.</span></span>  
  
 [<span data-ttu-id="d65c9-111">如何：使用采用参数的存储过程</span><span class="sxs-lookup"><span data-stu-id="d65c9-111">How to: Use Stored Procedures that Take Parameters</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-that-take-parameters.md)  
 <span data-ttu-id="d65c9-112">介绍如何使用输入和输出参数。</span><span class="sxs-lookup"><span data-stu-id="d65c9-112">Describes how to use input and output parameters.</span></span>  
  
 [<span data-ttu-id="d65c9-113">如何：使用针对多个结果形状映射的存储过程</span><span class="sxs-lookup"><span data-stu-id="d65c9-113">How to: Use Stored Procedures Mapped for Multiple Result Shapes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)  
 <span data-ttu-id="d65c9-114">介绍如何实现在同一存储过程中返回多个形状。</span><span class="sxs-lookup"><span data-stu-id="d65c9-114">Describes how to provide for returns of multiple shapes in the same stored procedure.</span></span>  
  
 [<span data-ttu-id="d65c9-115">如何：使用针对顺序的结果形状映射的存储过程</span><span class="sxs-lookup"><span data-stu-id="d65c9-115">How to: Use Stored Procedures Mapped for Sequential Result Shapes</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md)  
 <span data-ttu-id="d65c9-116">介绍如何在返回顺序已知的情况下提供多个形状。</span><span class="sxs-lookup"><span data-stu-id="d65c9-116">Describes how to provide for multiple shapes where the return sequence is known.</span></span>  
  
 [<span data-ttu-id="d65c9-117">通过使用存储过程自定义操作</span><span class="sxs-lookup"><span data-stu-id="d65c9-117">Customizing Operations By Using Stored Procedures</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md)  
 <span data-ttu-id="d65c9-118">介绍如何使用存储过程来实现插入、更新和删除操作。</span><span class="sxs-lookup"><span data-stu-id="d65c9-118">Describes how to use stored procedures to implement insert, update, and delete operations.</span></span>  
  
 [<span data-ttu-id="d65c9-119">通过仅使用存储过程自定义操作</span><span class="sxs-lookup"><span data-stu-id="d65c9-119">Customizing Operations by Using Stored Procedures Exclusively</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures-exclusively.md)  
 <span data-ttu-id="d65c9-120">介绍如何只使用存储过程来实现插入、更新和删除操作。</span><span class="sxs-lookup"><span data-stu-id="d65c9-120">Describes how to use nothing but stored procedures to implement insert, update, and delete operations.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d65c9-121">相关章节</span><span class="sxs-lookup"><span data-stu-id="d65c9-121">Related Sections</span></span>  
 [<span data-ttu-id="d65c9-122">编程指南</span><span class="sxs-lookup"><span data-stu-id="d65c9-122">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="d65c9-123">提供有关如何创建和使用 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 对象模型的信息。</span><span class="sxs-lookup"><span data-stu-id="d65c9-123">Provides information about how to create and use your [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="d65c9-124">演练：仅使用存储过程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d65c9-124">Walkthrough: Using Only Stored Procedures (Visual Basic)</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-visual-basic.md)  
 <span data-ttu-id="d65c9-125">包含了演示如何在 Visual Basic 中使用存储过程的步骤。</span><span class="sxs-lookup"><span data-stu-id="d65c9-125">Includes procedures that illustrate how to use stored procedures in Visual Basic.</span></span>  
  
 [<span data-ttu-id="d65c9-126">演练：仅使用存储过程 (C#)</span><span class="sxs-lookup"><span data-stu-id="d65c9-126">Walkthrough: Using Only Stored Procedures (C#)</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-csharp.md)  
 <span data-ttu-id="d65c9-127">包含了演示如何在 C# 中使用存储过程的步骤。</span><span class="sxs-lookup"><span data-stu-id="d65c9-127">Includes procedures that illustrate how to use stored procedures in C#.</span></span>
