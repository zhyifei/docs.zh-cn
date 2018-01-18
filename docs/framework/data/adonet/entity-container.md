---
title: "Entity Container — 实体容器"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 16e80405-2c75-42fc-b0e4-b1df53b1c584
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 10e10e0a5891e9383b3a8c6dafa6e19606486b33
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="entity-container"></a><span data-ttu-id="04066-102">Entity Container — 实体容器</span><span class="sxs-lookup"><span data-stu-id="04066-102">entity container</span></span>
<span data-ttu-id="04066-103">*实体容器*是的逻辑分组的[实体集](../../../../docs/framework/data/adonet/entity-set.md)，[关联集](../../../../docs/framework/data/adonet/association-set.md)，和[函数导入](../../../../docs/framework/data/adonet/model-declared-function.md)。</span><span class="sxs-lookup"><span data-stu-id="04066-103">An *entity container* is a logical grouping of [entity sets](../../../../docs/framework/data/adonet/entity-set.md), [association sets](../../../../docs/framework/data/adonet/association-set.md), and [function imports](../../../../docs/framework/data/adonet/model-declared-function.md).</span></span>  
  
 <span data-ttu-id="04066-104">对于在概念模型中定义的实体容器，必须满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="04066-104">The following must be true of an entity container defined in a conceptual model:</span></span>  
  
-   <span data-ttu-id="04066-105">在每个概念模型中必须至少定义一个实体容器。</span><span class="sxs-lookup"><span data-stu-id="04066-105">At least one entity container must be defined in each conceptual model.</span></span>  
  
-   <span data-ttu-id="04066-106">每个概念模型中的实体容器必须有唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="04066-106">The entity container must have a unique name within each conceptual model.</span></span>  
  
 <span data-ttu-id="04066-107">实体容器可以定义使用在一个或多个命名空间中定义的实体类型或关联的实体集或关联集。</span><span class="sxs-lookup"><span data-stu-id="04066-107">An entity container can define entity sets or association sets that use entity types or associations defined in one or more namespaces.</span></span> <span data-ttu-id="04066-108">有关详细信息，请参阅[实体数据模型： 命名空间](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md)。</span><span class="sxs-lookup"><span data-stu-id="04066-108">For more information, see [Entity Data Model: Namespaces](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="04066-109">示例</span><span class="sxs-lookup"><span data-stu-id="04066-109">Example</span></span>  
 <span data-ttu-id="04066-110">下图显示了一个具有三个实体类型的概念模型：`Book`、`Publisher` 和 `Author`。</span><span class="sxs-lookup"><span data-stu-id="04066-110">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  <span data-ttu-id="04066-111">有关更多信息，请参见下一个示例。</span><span class="sxs-lookup"><span data-stu-id="04066-111">See the next example for more information.</span></span>  
  
 <span data-ttu-id="04066-112">![示例模型](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="04066-112">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="04066-113">虽然该图没有传达实体容器信息，但概念模型必须定义一个实体容器。</span><span class="sxs-lookup"><span data-stu-id="04066-113">Although the diagram does not convey entity container information, the conceptual model must define an entity container.</span></span> <span data-ttu-id="04066-114">[ADO.NET 实体框架](../../../../docs/framework/data/adonet/ef/index.md)使用 DSL 称为概念架构定义语言 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 来定义概念模型。</span><span class="sxs-lookup"><span data-stu-id="04066-114">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a DSL called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="04066-115">下面的 CSDL 为上图所示的概念模型定义了一个实体容器。</span><span class="sxs-lookup"><span data-stu-id="04066-115">The following CSDL defines an entity container for the conceptual model shown in the diagram above.</span></span> <span data-ttu-id="04066-116">请注意，实体容器名称是在一个 XML 特性中定义的。</span><span class="sxs-lookup"><span data-stu-id="04066-116">Note that the entity container name is defined in an XML attribute.</span></span>  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a><span data-ttu-id="04066-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="04066-117">See Also</span></span>  
 [<span data-ttu-id="04066-118">实体数据模型关键概念</span><span class="sxs-lookup"><span data-stu-id="04066-118">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="04066-119">实体数据模型</span><span class="sxs-lookup"><span data-stu-id="04066-119">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
