---
title: 模型声明函数
ms.date: 03/30/2017
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
ms.openlocfilehash: cb2fca52604bd57f25469f5621c292a27638c76f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794799"
---
# <a name="model-declared-function"></a><span data-ttu-id="0069c-102">模型声明函数</span><span class="sxs-lookup"><span data-stu-id="0069c-102">model-declared function</span></span>
<span data-ttu-id="0069c-103">*模型声明函数*是在概念模型中声明的、但未在该概念模型中定义的函数。</span><span class="sxs-lookup"><span data-stu-id="0069c-103">A *model-declared function* is a function that is declared in a conceptual model, but is not defined in that conceptual model.</span></span> <span data-ttu-id="0069c-104">该函数可能是在承载或存储环境中定义的。</span><span class="sxs-lookup"><span data-stu-id="0069c-104">The function might be defined in the hosting or storage environment.</span></span> <span data-ttu-id="0069c-105">例如，模型声明函数可能映射至在数据库中定义的函数，从而在概念模型中提供服务器端的功能。</span><span class="sxs-lookup"><span data-stu-id="0069c-105">For example, a model-declared function might be mapped to a function that is defined in a database, thus exposing server-side functionality in the conceptual model.</span></span>  
  
 <span data-ttu-id="0069c-106">模型声明函数的声明包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="0069c-106">The declaration of a model-declared function contains the following information:</span></span>  
  
- <span data-ttu-id="0069c-107">函数名。</span><span class="sxs-lookup"><span data-stu-id="0069c-107">The name of the function.</span></span> <span data-ttu-id="0069c-108">（必需）</span><span class="sxs-lookup"><span data-stu-id="0069c-108">(Required)</span></span>  
  
- <span data-ttu-id="0069c-109">返回值的类型。</span><span class="sxs-lookup"><span data-stu-id="0069c-109">The type of the return value.</span></span> <span data-ttu-id="0069c-110">（可选）</span><span class="sxs-lookup"><span data-stu-id="0069c-110">(Optional)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="0069c-111">如果未指定返回值，则返回类型为 void。</span><span class="sxs-lookup"><span data-stu-id="0069c-111">If no return value is specified, the return type is void.</span></span>  
  
- <span data-ttu-id="0069c-112">参数信息，包括参数名和类型。</span><span class="sxs-lookup"><span data-stu-id="0069c-112">Parameter information, including parameter name and type.</span></span> <span data-ttu-id="0069c-113">（可选）</span><span class="sxs-lookup"><span data-stu-id="0069c-113">(Optional)</span></span>  
  
## <a name="example"></a><span data-ttu-id="0069c-114">示例</span><span class="sxs-lookup"><span data-stu-id="0069c-114">Example</span></span>  
 <span data-ttu-id="0069c-115">[ADO.NET 实体框架](./ef/index.md)使用一种称为概念架构定义语言（[CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)）的域特定语言（DSL）来定义概念模型。</span><span class="sxs-lookup"><span data-stu-id="0069c-115">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="0069c-116">在 CSDL 中，模型声明函数的一个实现是函数导入（使用[FunctionImport 元素](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl)）。</span><span class="sxs-lookup"><span data-stu-id="0069c-116">In CSDL, one implementation of a model-declared function is a function import (using the [FunctionImport element](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl)).</span></span> <span data-ttu-id="0069c-117">下面的 CSDL 定义了一个实体容器，其中包含一个函数导入定义。</span><span class="sxs-lookup"><span data-stu-id="0069c-117">The following CSDL defines an entity container with a function import definition.</span></span> <span data-ttu-id="0069c-118">请注意，由于未指定返回类型，因而该函数的返回类型为 void。</span><span class="sxs-lookup"><span data-stu-id="0069c-118">Note that the return type for the function is void since no return type is specified.</span></span>  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a><span data-ttu-id="0069c-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="0069c-119">See also</span></span>

- [<span data-ttu-id="0069c-120">实体数据模型关键概念</span><span class="sxs-lookup"><span data-stu-id="0069c-120">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="0069c-121">实体数据模型</span><span class="sxs-lookup"><span data-stu-id="0069c-121">Entity Data Model</span></span>](entity-data-model.md)
