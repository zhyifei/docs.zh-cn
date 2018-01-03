---
title: "用户定义的函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3304c9b2-5c7a-4a95-9d45-4f260dcb606e
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 833ffbbccfb35fd51ddde5dbeb4e3de3d79923ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="user-defined-functions"></a><span data-ttu-id="61977-102">用户定义的函数</span><span class="sxs-lookup"><span data-stu-id="61977-102">User-Defined Functions</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="61977-103"> 在您的对象模型中使用方法来表示用户定义的函数。</span><span class="sxs-lookup"><span data-stu-id="61977-103"> uses methods in your object model to represent user-defined functions.</span></span> <span data-ttu-id="61977-104">您可以通过应用 <xref:System.Data.Linq.Mapping.FunctionAttribute> 属性和 <xref:System.Data.Linq.Mapping.ParameterAttribute> 属性（如果需要）将方法指定为函数。</span><span class="sxs-lookup"><span data-stu-id="61977-104">You designate methods as functions by applying the <xref:System.Data.Linq.Mapping.FunctionAttribute> attribute and, where required, the <xref:System.Data.Linq.Mapping.ParameterAttribute> attribute.</span></span> <span data-ttu-id="61977-105">有关详细信息，请参阅[LINQ to SQL 对象模型](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)。</span><span class="sxs-lookup"><span data-stu-id="61977-105">For more information, see [The LINQ to SQL Object Model](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).</span></span>  
  
 <span data-ttu-id="61977-106">为避免出现 <xref:System.InvalidOperationException>，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中用户定义的函数必须采用以下形式之一：</span><span class="sxs-lookup"><span data-stu-id="61977-106">To avoid an <xref:System.InvalidOperationException>, user-defined functions in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] must be in one of the following forms:</span></span>  
  
-   <span data-ttu-id="61977-107">包装为具有正确映射属性的方法调用的函数。</span><span class="sxs-lookup"><span data-stu-id="61977-107">A function wrapped as a method call having the correct mapping attributes.</span></span> <span data-ttu-id="61977-108">有关详细信息，请参阅[基于属性的映射](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)。</span><span class="sxs-lookup"><span data-stu-id="61977-108">For more information, see [Attribute-Based Mapping](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).</span></span>  
  
-   <span data-ttu-id="61977-109">特定于 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 的静态 SQL 方法。</span><span class="sxs-lookup"><span data-stu-id="61977-109">A static SQL method specific to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
-   <span data-ttu-id="61977-110">[!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] 方法支持的函数。</span><span class="sxs-lookup"><span data-stu-id="61977-110">A function supported by a [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] method.</span></span>  
  
 <span data-ttu-id="61977-111">本节中的主题说明了在您自行编写代码的情况下，如何在您的应用程序中构建和调用这些方法。</span><span class="sxs-lookup"><span data-stu-id="61977-111">The topics in this section show how to form and call these methods in your application if you write the code yourself.</span></span> <span data-ttu-id="61977-112">使用 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] 的开发人员通常会使用 [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] 来映射用户定义的函数。</span><span class="sxs-lookup"><span data-stu-id="61977-112">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] would typically use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to map user-defined functions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="61977-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="61977-113">In This Section</span></span>  
 [<span data-ttu-id="61977-114">如何：使用标量值用户定义的函数</span><span class="sxs-lookup"><span data-stu-id="61977-114">How to: Use Scalar-Valued User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-scalar-valued-user-defined-functions.md)  
 <span data-ttu-id="61977-115">介绍如何实现返回标量值的函数。</span><span class="sxs-lookup"><span data-stu-id="61977-115">Describes how to implement a function that returns scalar values.</span></span>  
  
 [<span data-ttu-id="61977-116">如何：使用表值用户定义的函数</span><span class="sxs-lookup"><span data-stu-id="61977-116">How to: Use Table-Valued User-Defined Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-table-valued-user-defined-functions.md)  
 <span data-ttu-id="61977-117">介绍如何实现返回表值的函数。</span><span class="sxs-lookup"><span data-stu-id="61977-117">Describes how to implement a function that returns table values.</span></span>  
  
 [<span data-ttu-id="61977-118">如何：以内联方式调用用户定义的函数</span><span class="sxs-lookup"><span data-stu-id="61977-118">How to: Call User-Defined Functions Inline</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/how-to-call-user-defined-functions-inline.md)  
 <span data-ttu-id="61977-119">介绍如何对函数进行内联调用，以及进行内联调用时在执行方面的差异。</span><span class="sxs-lookup"><span data-stu-id="61977-119">Describes how to make inline calls to functions and the differences in execution when the call is made inline.</span></span>
