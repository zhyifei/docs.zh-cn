---
title: 关联端重数
ms.date: 03/30/2017
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
ms.openlocfilehash: 183bbafaf1de3adf8719c7ee562be3513832ef10
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2019
ms.locfileid: "58412092"
---
# <a name="association-end-multiplicity"></a><span data-ttu-id="e174b-102">关联端重数</span><span class="sxs-lookup"><span data-stu-id="e174b-102">association end multiplicity</span></span>
<span data-ttu-id="e174b-103">*关联端重*定义的数字[实体类型](../../../../docs/framework/data/adonet/entity-type.md)一端可以存在的实例[关联](../../../../docs/framework/data/adonet/association-type.md)。</span><span class="sxs-lookup"><span data-stu-id="e174b-103">*Association end multiplicity* defines the number of [entity type](../../../../docs/framework/data/adonet/entity-type.md) instances that can be at one end of an [association](../../../../docs/framework/data/adonet/association-type.md).</span></span>  
  
 <span data-ttu-id="e174b-104">关联端重数可以具有下列值之一：</span><span class="sxs-lookup"><span data-stu-id="e174b-104">An association end multiplicity can have one of the following values:</span></span>  
  
-   <span data-ttu-id="e174b-105">一 (1):指示在关联端存在的一个实体类型实例。</span><span class="sxs-lookup"><span data-stu-id="e174b-105">one (1): Indicates that exactly one entity type instance exists at the association end.</span></span>  
  
-   <span data-ttu-id="e174b-106">零或一 (0..1):指示在关联端存在零个或一个实体类型实例。</span><span class="sxs-lookup"><span data-stu-id="e174b-106">zero or one (0..1): Indicates that zero or one entity type instances exist at the association end.</span></span>  
  
-   <span data-ttu-id="e174b-107">很多 (\*):指示在关联端存在零行、 一行或多个实体类型实例。</span><span class="sxs-lookup"><span data-stu-id="e174b-107">many (\*): Indicates that zero, one, or more entity type instances exist at the association end.</span></span>  
  
 <span data-ttu-id="e174b-108">关联的特征通常由关联端重数表示。</span><span class="sxs-lookup"><span data-stu-id="e174b-108">An association is often characterized by its association end multiplicities.</span></span> <span data-ttu-id="e174b-109">例如，如果关联端有一 （1） 和许多的重数 (\*)，该关联称为一个对多关联。</span><span class="sxs-lookup"><span data-stu-id="e174b-109">For example, if the ends of an association have multiplicities one (1) and many (\*), the association is called a one-to-many association.</span></span> <span data-ttu-id="e174b-110">在下面的示例中，`PublishedBy` 关联是一个一对多关联（一个出版商可以出版很多书，而一本书只能由一个出版商出版）。</span><span class="sxs-lookup"><span data-stu-id="e174b-110">In the example below, the `PublishedBy` association is a one-to-many association (a publisher publishes many books and a book is published by one publisher).</span></span> <span data-ttu-id="e174b-111">
  `WrittenBy\` 关联是一个多对多关联（一本书可以有多位作者，而一位作者可以著有多本书）。</span><span class="sxs-lookup"><span data-stu-id="e174b-111">The `WrittenBy` association is a many-to-many association (a book can have multiple authors and an author can write multiple books).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e174b-112">示例</span><span class="sxs-lookup"><span data-stu-id="e174b-112">Example</span></span>  
 <span data-ttu-id="e174b-113">下图显示了一个具有两个关联的概念模型：`PublishedBy` 和 `WrittenBy`。</span><span class="sxs-lookup"><span data-stu-id="e174b-113">The diagram below shows a conceptual model with two associations: `PublishedBy` and `WrittenBy`.</span></span> <span data-ttu-id="e174b-114">
  `PublishedBy\` 关联的关联端是 `Book` 和 `Publisher\` 实体类型。</span><span class="sxs-lookup"><span data-stu-id="e174b-114">The association ends for the `PublishedBy` association are the `Book` and `Publisher` entity types.</span></span> <span data-ttu-id="e174b-115">多重性`Publisher`最终为一 (1) 和重数`Book`最终为多个 (\*)。</span><span class="sxs-lookup"><span data-stu-id="e174b-115">The multiplicity of the `Publisher` end is one (1) and the multiplicity of the `Book` end is many (\*).</span></span>  
  
 ![具有三个实体类型的示例模型](./media/association-end-multiplicity/example-model-three-entity-types.gif)  
  
 <span data-ttu-id="e174b-117">ADO.NET 实体框架使用称为概念性架构定义语言的特定于域的语言 (DSL) ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 来定义概念模型。</span><span class="sxs-lookup"><span data-stu-id="e174b-117">The ADO.NET Entity Framework uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="e174b-118">下面的 CSDL 定义了上图中显示的 `PublishedBy` 关联：</span><span class="sxs-lookup"><span data-stu-id="e174b-118">The following CSDL defines the `PublishedBy` association shown in the diagram above:</span></span>  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a><span data-ttu-id="e174b-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="e174b-119">See also</span></span>
- [<span data-ttu-id="e174b-120">实体数据模型关键概念</span><span class="sxs-lookup"><span data-stu-id="e174b-120">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="e174b-121">实体数据模型</span><span class="sxs-lookup"><span data-stu-id="e174b-121">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
