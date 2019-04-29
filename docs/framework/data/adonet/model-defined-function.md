---
title: 模型定义函数
ms.date: 03/30/2017
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
ms.openlocfilehash: 77152e8f37b009cbc3e72f053ead867914768d3d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772226"
---
# <a name="model-defined-function"></a><span data-ttu-id="5e4bc-102">模型定义函数</span><span class="sxs-lookup"><span data-stu-id="5e4bc-102">model-defined function</span></span>
<span data-ttu-id="5e4bc-103">一个*模型定义函数*是概念模型中定义的函数。</span><span class="sxs-lookup"><span data-stu-id="5e4bc-103">A *model-defined function* is a function that is defined in a conceptual model.</span></span> <span data-ttu-id="5e4bc-104">以表示模型定义函数的正文[Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)、 允许使用函数表示为独立于规则或数据源中支持的语言。</span><span class="sxs-lookup"><span data-stu-id="5e4bc-104">The body of a model-defined function is expressed in [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md), which allows for the function to be expressed independently of rules or languages supported in the data source.</span></span>  
  
 <span data-ttu-id="5e4bc-105">模型定义函数的定义包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="5e4bc-105">A definition for a model-defined function contains the following information:</span></span>  
  
- <span data-ttu-id="5e4bc-106">函数名。</span><span class="sxs-lookup"><span data-stu-id="5e4bc-106">A function name.</span></span> <span data-ttu-id="5e4bc-107">（必需）</span><span class="sxs-lookup"><span data-stu-id="5e4bc-107">(Required)</span></span>  
  
- <span data-ttu-id="5e4bc-108">返回值的类型。</span><span class="sxs-lookup"><span data-stu-id="5e4bc-108">The type of the return value.</span></span> <span data-ttu-id="5e4bc-109">（可选）</span><span class="sxs-lookup"><span data-stu-id="5e4bc-109">(Optional)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5e4bc-110">如果未指定返回类型，则返回值为 void。</span><span class="sxs-lookup"><span data-stu-id="5e4bc-110">If no return type is specified, the return value is void.</span></span>  
  
- <span data-ttu-id="5e4bc-111">参数信息。</span><span class="sxs-lookup"><span data-stu-id="5e4bc-111">Parameter information.</span></span> <span data-ttu-id="5e4bc-112">（可选）</span><span class="sxs-lookup"><span data-stu-id="5e4bc-112">(Optional)</span></span>  
  
- <span data-ttu-id="5e4bc-113">[Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)定义函数的正文的表达式。</span><span class="sxs-lookup"><span data-stu-id="5e4bc-113">An [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md) expression that defines the body of the function.</span></span>  
  
 <span data-ttu-id="5e4bc-114">请注意，模型定义函数不支持输出参数。</span><span class="sxs-lookup"><span data-stu-id="5e4bc-114">Note that model-defined functions do not support output parameters.</span></span> <span data-ttu-id="5e4bc-115">这一限制可以保证无法对模型定义函数进行编写。</span><span class="sxs-lookup"><span data-stu-id="5e4bc-115">This restriction is in place so that model-defined functions can be composed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e4bc-116">示例</span><span class="sxs-lookup"><span data-stu-id="5e4bc-116">Example</span></span>  
 <span data-ttu-id="5e4bc-117">下图显示了一个具有三个实体类型的概念模型：`Book`、`Publisher` 和 `Author`。</span><span class="sxs-lookup"><span data-stu-id="5e4bc-117">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  
  
 ![显示具有发布日期的模型的屏幕截图。](./media/model-defined-function/model-published-date-three-entity-types.gif)  
  
 <span data-ttu-id="5e4bc-119">[ADO.NET 实体框架](../../../../docs/framework/data/adonet/ef/index.md)使用称为概念性架构定义语言的特定于域的语言 (DSL) ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 来定义概念模型。</span><span class="sxs-lookup"><span data-stu-id="5e4bc-119">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="5e4bc-120">下面的 CSDL 在概念模型中定义了一个函数，它返回自某个 `Book` 实例（如上图所示）出版以来的年数。</span><span class="sxs-lookup"><span data-stu-id="5e4bc-120">The following CSDL defines a function in the conceptual model that returns the numbers of years since an instance of a `Book` (in the diagram above) was published.</span></span>  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a><span data-ttu-id="5e4bc-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="5e4bc-121">See also</span></span>

- [<span data-ttu-id="5e4bc-122">实体数据模型关键概念</span><span class="sxs-lookup"><span data-stu-id="5e4bc-122">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="5e4bc-123">实体数据模型</span><span class="sxs-lookup"><span data-stu-id="5e4bc-123">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
- [<span data-ttu-id="5e4bc-124">实体数据模型：基元数据类型</span><span class="sxs-lookup"><span data-stu-id="5e4bc-124">Entity Data Model: Primitive Data Types</span></span>](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)
