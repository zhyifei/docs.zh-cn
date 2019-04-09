---
title: 模型声明函数
ms.date: 03/30/2017
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
ms.openlocfilehash: c9abf9a3340cd22ab5d654588b1d22e10b5c05fa
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130541"
---
# <a name="model-declared-function"></a><span data-ttu-id="15863-102">模型声明函数</span><span class="sxs-lookup"><span data-stu-id="15863-102">model-declared function</span></span>
<span data-ttu-id="15863-103">一个*模型声明函数*是在概念模型中，声明但未在该概念模型中定义的函数。</span><span class="sxs-lookup"><span data-stu-id="15863-103">A *model-declared function* is a function that is declared in a conceptual model, but is not defined in that conceptual model.</span></span> <span data-ttu-id="15863-104">该函数可能是在承载或存储环境中定义的。</span><span class="sxs-lookup"><span data-stu-id="15863-104">The function might be defined in the hosting or storage environment.</span></span> <span data-ttu-id="15863-105">例如，模型声明函数可能映射至在数据库中定义的函数，从而在概念模型中提供服务器端的功能。</span><span class="sxs-lookup"><span data-stu-id="15863-105">For example, a model-declared function might be mapped to a function that is defined in a database, thus exposing server-side functionality in the conceptual model.</span></span>  
  
 <span data-ttu-id="15863-106">模型声明函数的声明包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="15863-106">The declaration of a model-declared function contains the following information:</span></span>  
  
-   <span data-ttu-id="15863-107">函数名。</span><span class="sxs-lookup"><span data-stu-id="15863-107">The name of the function.</span></span> <span data-ttu-id="15863-108">（必需）</span><span class="sxs-lookup"><span data-stu-id="15863-108">(Required)</span></span>  
  
-   <span data-ttu-id="15863-109">返回值的类型。</span><span class="sxs-lookup"><span data-stu-id="15863-109">The type of the return value.</span></span> <span data-ttu-id="15863-110">（可选）</span><span class="sxs-lookup"><span data-stu-id="15863-110">(Optional)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="15863-111">如果未指定返回值，则返回类型为 void。</span><span class="sxs-lookup"><span data-stu-id="15863-111">If no return value is specified, the return type is void.</span></span>  
  
-   <span data-ttu-id="15863-112">参数信息，包括参数名和类型。</span><span class="sxs-lookup"><span data-stu-id="15863-112">Parameter information, including parameter name and type.</span></span> <span data-ttu-id="15863-113">（可选）</span><span class="sxs-lookup"><span data-stu-id="15863-113">(Optional)</span></span>  
  
## <a name="example"></a><span data-ttu-id="15863-114">示例</span><span class="sxs-lookup"><span data-stu-id="15863-114">Example</span></span>  
 <span data-ttu-id="15863-115">[ADO.NET 实体框架](./ef/index.md)使用称为概念性架构定义语言的特定于域的语言 (DSL) ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) 来定义概念模型。</span><span class="sxs-lookup"><span data-stu-id="15863-115">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="15863-116">在 CSDL 中，模型声明函数的一种实现是函数导入 (使用[FunctionImport 元素](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl))。</span><span class="sxs-lookup"><span data-stu-id="15863-116">In CSDL, one implementation of a model-declared function is a function import (using the [FunctionImport element](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl)).</span></span> <span data-ttu-id="15863-117">下面的 CSDL 定义了一个实体容器，其中包含一个函数导入定义。</span><span class="sxs-lookup"><span data-stu-id="15863-117">The following CSDL defines an entity container with a function import definition.</span></span> <span data-ttu-id="15863-118">请注意，由于未指定返回类型，因而该函数的返回类型为 void。</span><span class="sxs-lookup"><span data-stu-id="15863-118">Note that the return type for the function is void since no return type is specified.</span></span>  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a><span data-ttu-id="15863-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="15863-119">See also</span></span>

- [<span data-ttu-id="15863-120">实体数据模型关键概念</span><span class="sxs-lookup"><span data-stu-id="15863-120">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="15863-121">实体数据模型</span><span class="sxs-lookup"><span data-stu-id="15863-121">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
