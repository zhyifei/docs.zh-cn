---
title: "模型声明函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0e47c89524bf149d862ae872c0c5956b7debd818
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="model-declared-function"></a><span data-ttu-id="011e0-102">模型声明函数</span><span class="sxs-lookup"><span data-stu-id="011e0-102">model-declared function</span></span>
<span data-ttu-id="011e0-103">A*模型声明函数*是在概念模型中，声明但未在该概念模型中定义的函数。</span><span class="sxs-lookup"><span data-stu-id="011e0-103">A *model-declared function* is a function that is declared in a conceptual model, but is not defined in that conceptual model.</span></span> <span data-ttu-id="011e0-104">该函数可能是在承载或存储环境中定义的。</span><span class="sxs-lookup"><span data-stu-id="011e0-104">The function might be defined in the hosting or storage environment.</span></span> <span data-ttu-id="011e0-105">例如，模型声明函数可能映射至在数据库中定义的函数，从而在概念模型中提供服务器端的功能。</span><span class="sxs-lookup"><span data-stu-id="011e0-105">For example, a model-declared function might be mapped to a function that is defined in a database, thus exposing server-side functionality in the conceptual model.</span></span>  
  
 <span data-ttu-id="011e0-106">模型声明函数的声明包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="011e0-106">The declaration of a model-declared function contains the following information:</span></span>  
  
-   <span data-ttu-id="011e0-107">函数名。</span><span class="sxs-lookup"><span data-stu-id="011e0-107">The name of the function.</span></span> <span data-ttu-id="011e0-108">（必需）</span><span class="sxs-lookup"><span data-stu-id="011e0-108">(Required)</span></span>  
  
-   <span data-ttu-id="011e0-109">返回值的类型。</span><span class="sxs-lookup"><span data-stu-id="011e0-109">The type of the return value.</span></span> <span data-ttu-id="011e0-110">（可选）</span><span class="sxs-lookup"><span data-stu-id="011e0-110">(Optional)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="011e0-111">如果未指定返回值，则返回类型为 void。</span><span class="sxs-lookup"><span data-stu-id="011e0-111">If no return value is specified, the return type is void.</span></span>  
  
-   <span data-ttu-id="011e0-112">参数信息，包括参数名和类型。</span><span class="sxs-lookup"><span data-stu-id="011e0-112">Parameter information, including parameter name and type.</span></span> <span data-ttu-id="011e0-113">（可选）</span><span class="sxs-lookup"><span data-stu-id="011e0-113">(Optional)</span></span>  
  
## <a name="example"></a><span data-ttu-id="011e0-114">示例</span><span class="sxs-lookup"><span data-stu-id="011e0-114">Example</span></span>  
 <span data-ttu-id="011e0-115">[ADO.NET 实体框架](../../../../docs/framework/data/adonet/ef/index.md)使用域特定语言 (DSL) 称为概念架构定义语言 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 来定义概念模型。</span><span class="sxs-lookup"><span data-stu-id="011e0-115">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="011e0-116">在 CSDL 中，模型声明函数的一种实现是[函数导入](http://msdn.microsoft.com/en-us/125704ae-56c7-4233-80b7-389a10f3a65d)。</span><span class="sxs-lookup"><span data-stu-id="011e0-116">In CSDL, one implementation of a model-declared function is a [function import](http://msdn.microsoft.com/en-us/125704ae-56c7-4233-80b7-389a10f3a65d).</span></span> <span data-ttu-id="011e0-117">下面的 CSDL 定义了一个实体容器，其中包含一个函数导入定义。</span><span class="sxs-lookup"><span data-stu-id="011e0-117">The following CSDL defines an entity container with a function import definition.</span></span> <span data-ttu-id="011e0-118">请注意，由于未指定返回类型，因而该函数的返回类型为 void。</span><span class="sxs-lookup"><span data-stu-id="011e0-118">Note that the return type for the function is void since no return type is specified.</span></span>  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a><span data-ttu-id="011e0-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="011e0-119">See Also</span></span>  
 [<span data-ttu-id="011e0-120">实体数据模型关键概念</span><span class="sxs-lookup"><span data-stu-id="011e0-120">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="011e0-121">实体数据模型</span><span class="sxs-lookup"><span data-stu-id="011e0-121">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
