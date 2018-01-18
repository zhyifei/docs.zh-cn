---
title: "关联端重数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 36f6d22a8fd3a3c0f1fd997d5101b9fdf8e91a8c
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="association-end-multiplicity"></a><span data-ttu-id="e07da-102">关联端重数</span><span class="sxs-lookup"><span data-stu-id="e07da-102">association end multiplicity</span></span>
<span data-ttu-id="e07da-103">*关联端重数*定义数[实体类型](../../../../docs/framework/data/adonet/entity-type.md)的一端可以存在的实例[关联](../../../../docs/framework/data/adonet/association-type.md)。</span><span class="sxs-lookup"><span data-stu-id="e07da-103">*Association end multiplicity* defines the number of [entity type](../../../../docs/framework/data/adonet/entity-type.md) instances that can be at one end of an [association](../../../../docs/framework/data/adonet/association-type.md).</span></span>  
  
 <span data-ttu-id="e07da-104">关联端重数可以具有下列值之一：</span><span class="sxs-lookup"><span data-stu-id="e07da-104">An association end multiplicity can have one of the following values:</span></span>  
  
-   <span data-ttu-id="e07da-105">一 (1)：表明在关联端存在且只存在一个实体类型实例。</span><span class="sxs-lookup"><span data-stu-id="e07da-105">one (1): Indicates that exactly one entity type instance exists at the association end.</span></span>  
  
-   <span data-ttu-id="e07da-106">零或一 (0..1)：表明在关联端不存在实体类型实例或存在一个实体类型实例。</span><span class="sxs-lookup"><span data-stu-id="e07da-106">zero or one (0..1): Indicates that zero or one entity type instances exist at the association end.</span></span>  
  
-   <span data-ttu-id="e07da-107">多 (\*)：表明在关联端不存在实体类型实例，或者存在一个或多个实体类型实例。</span><span class="sxs-lookup"><span data-stu-id="e07da-107">many (\*): Indicates that zero, one, or more entity type instances exist at the association end.</span></span>  
  
 <span data-ttu-id="e07da-108">关联的特征通常由关联端重数表示。</span><span class="sxs-lookup"><span data-stu-id="e07da-108">An association is often characterized by its association end multiplicities.</span></span> <span data-ttu-id="e07da-109">例如，如果某个关联的两端的重数分别为“一 (1)”和“多 (\*)”，则该关联称为一对多关联。</span><span class="sxs-lookup"><span data-stu-id="e07da-109">For example, if the ends of an association have multiplicities one (1) and many (\*), the association is called a one-to-many association.</span></span> <span data-ttu-id="e07da-110">在下面的示例中，`PublishedBy` 关联是一个一对多关联（一个出版商可以出版很多书，而一本书只能由一个出版商出版）。</span><span class="sxs-lookup"><span data-stu-id="e07da-110">In the example below, the `PublishedBy` association is a one-to-many association (a publisher publishes many books and a book is published by one publisher).</span></span> <span data-ttu-id="e07da-111">`WrittenBy` 关联是一个多对多关联（一本书可以有多位作者，而一位作者可以著有多本书）。</span><span class="sxs-lookup"><span data-stu-id="e07da-111">The `WrittenBy` association is a many-to-many association (a book can have multiple authors and an author can write multiple books).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e07da-112">示例</span><span class="sxs-lookup"><span data-stu-id="e07da-112">Example</span></span>  
 <span data-ttu-id="e07da-113">下图显示了一个具有两个关联的概念模型：`PublishedBy` 和 `WrittenBy`。</span><span class="sxs-lookup"><span data-stu-id="e07da-113">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="e07da-114">`PublishedBy` 关联的关联端是 `Book` 和 `Publisher` 实体类型。</span><span class="sxs-lookup"><span data-stu-id="e07da-114">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="e07da-115">`Publisher` 端的重数为“一 (1)”，`Book` 端的重数为“多 (\*)”。</span><span class="sxs-lookup"><span data-stu-id="e07da-115">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*).</span></span>  
  
 <span data-ttu-id="e07da-116">![示例模型](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span><span class="sxs-lookup"><span data-stu-id="e07da-116">![Example Model](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")</span></span>  
  
 <span data-ttu-id="e07da-117">ADO.NET 实体框架使用的域特定语言 (DSL) 称为概念架构定义语言 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 来定义概念模型。</span><span class="sxs-lookup"><span data-stu-id="e07da-117">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="e07da-118">下面的 CSDL 定义了上图中显示的 `PublishedBy` 关联：</span><span class="sxs-lookup"><span data-stu-id="e07da-118">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="e07da-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="e07da-119">See Also</span></span>  
 [<span data-ttu-id="e07da-120">实体数据模型关键概念</span><span class="sxs-lookup"><span data-stu-id="e07da-120">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="e07da-121">实体数据模型</span><span class="sxs-lookup"><span data-stu-id="e07da-121">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
