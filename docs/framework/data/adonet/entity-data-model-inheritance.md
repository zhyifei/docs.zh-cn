---
title: "实体数据模型：继承"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 42c7ef24-710a-4af9-8493-cd41c399ecb0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 15862f545092d0573b97b77d6cdb2e1fcdc33978
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="entity-data-model-inheritance"></a><span data-ttu-id="06bd2-102">实体数据模型：继承</span><span class="sxs-lookup"><span data-stu-id="06bd2-102">Entity Data Model: Inheritance</span></span>
<span data-ttu-id="06bd2-103">实体数据模型 (EDM) 支持的继承[实体类型](../../../../docs/framework/data/adonet/entity-type.md)。</span><span class="sxs-lookup"><span data-stu-id="06bd2-103">The Entity Data Model (EDM) supports inheritance for [entity types](../../../../docs/framework/data/adonet/entity-type.md).</span></span> <span data-ttu-id="06bd2-104">EDM 中的继承与面向对象的编程语言中的类的继承类似。</span><span class="sxs-lookup"><span data-stu-id="06bd2-104">Inheritance in the EDM is similar to inheritance for classes in object-oriented programming languages.</span></span> <span data-ttu-id="06bd2-105">像使用面向对象的语言中的类，在概念模型中可定义一个实体类型 (*派生类型*)，继承自另一个实体类型 (*基类型*)。</span><span class="sxs-lookup"><span data-stu-id="06bd2-105">Like with classes in object-oriented languages, in a conceptual model you can define an entity type (a *derived type*) that inherits from another entity type (the *base type*).</span></span> <span data-ttu-id="06bd2-106">但是，与面向对象编程中的类，不同的概念模型中的派生的类型始终会继承所有[属性](../../../../docs/framework/data/adonet/property.md)和[导航属性](../../../../docs/framework/data/adonet/navigation-property.md)的基类型。</span><span class="sxs-lookup"><span data-stu-id="06bd2-106">However, unlike classes in object-oriented programming, in a conceptual model the derived type always inherits all the [properties](../../../../docs/framework/data/adonet/property.md) and [navigation properties](../../../../docs/framework/data/adonet/navigation-property.md) of the base type.</span></span> <span data-ttu-id="06bd2-107">不能重写派生类型中的继承属性。</span><span class="sxs-lookup"><span data-stu-id="06bd2-107">You cannot override inherited properties in a derived type.</span></span>  
  
 <span data-ttu-id="06bd2-108">在概念模型中，可以构建继承层次结构，其中一个派生类型将继承自另一个派生类型。</span><span class="sxs-lookup"><span data-stu-id="06bd2-108">In a conceptual model you can build inheritance hierarchies in which a derived type inherits from another derived type.</span></span> <span data-ttu-id="06bd2-109">在层次结构 （不是派生的类型的层次结构中的一个类型） 的顶部的类型称为*根类型*。</span><span class="sxs-lookup"><span data-stu-id="06bd2-109">The type at the top of the hierarchy (the one type in the hierarchy that is not a derived type) is called the *root type*.</span></span> <span data-ttu-id="06bd2-110">继承层次结构，在[实体键](../../../../docs/framework/data/adonet/entity-key.md)必须在根类型上定义。</span><span class="sxs-lookup"><span data-stu-id="06bd2-110">In an inheritance hierarchy, the [entity key](../../../../docs/framework/data/adonet/entity-key.md) must be defined on the root type.</span></span>  
  
 <span data-ttu-id="06bd2-111">不能构建这样的继承层次结构，即一个派生类型继承自多个类型。</span><span class="sxs-lookup"><span data-stu-id="06bd2-111">You cannot build inheritance hierarchies in which a derived type inherits from more than one type.</span></span> <span data-ttu-id="06bd2-112">例如，在包含 `Book` 实体类型的概念模型中，可以定义都是继承自 `FictionBook` 的派生类型 `NonFictionBook` 和 `Book`。</span><span class="sxs-lookup"><span data-stu-id="06bd2-112">For example, in a conceptual model with a `Book` entity type, you could define derived types `FictionBook` and `NonFictionBook` that each inherit from `Book`.</span></span> <span data-ttu-id="06bd2-113">但是，随后不能定义同时继承自 `FictionBook` 和 `NonFictionBook` 类型的类型。</span><span class="sxs-lookup"><span data-stu-id="06bd2-113">However, you could not then define a type that inherits from both the `FictionBook` and `NonFictionBook` types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="06bd2-114">示例</span><span class="sxs-lookup"><span data-stu-id="06bd2-114">Example</span></span>  
 <span data-ttu-id="06bd2-115">下图显示了一个具有四个实体类型的概念模型：`Book`、`FictionBook`、`Publisher` 和 `Author`。</span><span class="sxs-lookup"><span data-stu-id="06bd2-115">The diagram below shows a conceptual model with four entity types: `Book`, `FictionBook`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="06bd2-116">`FictionBook` 实体类型是一个派生类型，继承自 `Book` 实体类型。</span><span class="sxs-lookup"><span data-stu-id="06bd2-116">The `FictionBook` entity type is a derived type, inheriting from the `Book` entity type.</span></span> <span data-ttu-id="06bd2-117">`FictionBook` 类型继承了 `ISBN (Key)`、`Title` 和 `Revision` 属性，并定义了一个名为 `Genre` 的附加属性。</span><span class="sxs-lookup"><span data-stu-id="06bd2-117">The `FictionBook` type inherits the `ISBN (Key)`, `Title`, and `Revision` properties, and defines an additional property called `Genre`.</span></span>  
  
 <span data-ttu-id="06bd2-118">![继承](../../../../docs/framework/data/adonet/media/inheritanceexample.gif "InheritanceExample")</span><span class="sxs-lookup"><span data-stu-id="06bd2-118">![Inheritance](../../../../docs/framework/data/adonet/media/inheritanceexample.gif "InheritanceExample")</span></span>  
  
 <span data-ttu-id="06bd2-119">[ADO.NET 实体框架](../../../../docs/framework/data/adonet/ef/index.md)使用域特定语言 (DSL) 称为概念架构定义语言 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 来定义概念模型。</span><span class="sxs-lookup"><span data-stu-id="06bd2-119">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="06bd2-120">下面的 CSDL 定义了一个实体类型 `FictionBook`，它继承自 `Book` 类型（如上图中所示）：</span><span class="sxs-lookup"><span data-stu-id="06bd2-120">The following CSDL defines an entity type, `FictionBook`, that inherits from the `Book` type (as in the diagram above):</span></span>  
  
 [!code-xml[EDM_Example_Model#DerivedType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books5.edmx#derivedtype)]  
  
## <a name="see-also"></a><span data-ttu-id="06bd2-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="06bd2-121">See Also</span></span>  
 [<span data-ttu-id="06bd2-122">实体数据模型关键概念</span><span class="sxs-lookup"><span data-stu-id="06bd2-122">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="06bd2-123">实体数据模型</span><span class="sxs-lookup"><span data-stu-id="06bd2-123">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
