---
title: 关联端重数
ms.date: 03/30/2017
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
ms.openlocfilehash: cdcf69e7118620b2f8febd02d7695d429bf8cc2c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786945"
---
# <a name="association-end-multiplicity"></a><span data-ttu-id="70a9b-102">关联端重数</span><span class="sxs-lookup"><span data-stu-id="70a9b-102">association end multiplicity</span></span>
<span data-ttu-id="70a9b-103">*关联 end 多重性*定义可以位于[关联](association-type.md)一端的[实体类型](entity-type.md)实例的数量。</span><span class="sxs-lookup"><span data-stu-id="70a9b-103">*Association end multiplicity* defines the number of [entity type](entity-type.md) instances that can be at one end of an [association](association-type.md).</span></span>  
  
 <span data-ttu-id="70a9b-104">关联端重数可以具有下列值之一：</span><span class="sxs-lookup"><span data-stu-id="70a9b-104">An association end multiplicity can have one of the following values:</span></span>  
  
- <span data-ttu-id="70a9b-105">一（1）：指示在关联端刚好存在一个实体类型实例。</span><span class="sxs-lookup"><span data-stu-id="70a9b-105">one (1): Indicates that exactly one entity type instance exists at the association end.</span></span>  
  
- <span data-ttu-id="70a9b-106">零或一（0 .. 1）：指示关联端存在零个或一个实体类型实例。</span><span class="sxs-lookup"><span data-stu-id="70a9b-106">zero or one (0..1): Indicates that zero or one entity type instances exist at the association end.</span></span>  
  
- <span data-ttu-id="70a9b-107">多（\*）：指示在关联端存在零个、一个或多个实体类型实例。</span><span class="sxs-lookup"><span data-stu-id="70a9b-107">many (\*): Indicates that zero, one, or more entity type instances exist at the association end.</span></span>  
  
 <span data-ttu-id="70a9b-108">关联的特征通常由关联端重数表示。</span><span class="sxs-lookup"><span data-stu-id="70a9b-108">An association is often characterized by its association end multiplicities.</span></span> <span data-ttu-id="70a9b-109">例如，如果关联端的重数为（1）和多（\*），则关联称为一对多关联。</span><span class="sxs-lookup"><span data-stu-id="70a9b-109">For example, if the ends of an association have multiplicities one (1) and many (\*), the association is called a one-to-many association.</span></span> <span data-ttu-id="70a9b-110">在下面的示例中，`PublishedBy` 关联是一个一对多关联（一个出版商可以出版很多书，而一本书只能由一个出版商出版）。</span><span class="sxs-lookup"><span data-stu-id="70a9b-110">In the example below, the `PublishedBy` association is a one-to-many association (a publisher publishes many books and a book is published by one publisher).</span></span> <span data-ttu-id="70a9b-111">`WrittenBy` 关联是一个多对多关联（一本书可以有多位作者，而一位作者可以著有多本书）。</span><span class="sxs-lookup"><span data-stu-id="70a9b-111">The `WrittenBy` association is a many-to-many association (a book can have multiple authors and an author can write multiple books).</span></span>  
  
## <a name="example"></a><span data-ttu-id="70a9b-112">示例</span><span class="sxs-lookup"><span data-stu-id="70a9b-112">Example</span></span>  
 <span data-ttu-id="70a9b-113">下图显示了一个具有两个关联的概念模型：`PublishedBy` 和 `WrittenBy`。</span><span class="sxs-lookup"><span data-stu-id="70a9b-113">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="70a9b-114">`PublishedBy` 关联的关联端是 `Book` 和 `Publisher` 实体类型。</span><span class="sxs-lookup"><span data-stu-id="70a9b-114">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="70a9b-115">`Publisher` End 的重数为一（1），而`Book`末尾的重数为 many （\*）。</span><span class="sxs-lookup"><span data-stu-id="70a9b-115">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*).</span></span>  
  
 ![具有三个实体类型的示例模型](./media/association-end-multiplicity/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="70a9b-117">ADO.NET 实体框架使用一种称为概念架构定义语言（[CSDL](./ef/language-reference/csdl-specification.md)）的域特定语言（DSL）来定义概念模型。</span><span class="sxs-lookup"><span data-stu-id="70a9b-117">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](./ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="70a9b-118">下面的 CSDL 定义了上图中显示的 `PublishedBy` 关联：</span><span class="sxs-lookup"><span data-stu-id="70a9b-118">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="70a9b-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="70a9b-119">See also</span></span>

- [<span data-ttu-id="70a9b-120">实体数据模型关键概念</span><span class="sxs-lookup"><span data-stu-id="70a9b-120">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="70a9b-121">实体数据模型</span><span class="sxs-lookup"><span data-stu-id="70a9b-121">Entity Data Model</span></span>](entity-data-model.md)
