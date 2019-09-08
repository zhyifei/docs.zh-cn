---
title: 实体数据模型：继承
ms.date: 03/30/2017
ms.assetid: 42c7ef24-710a-4af9-8493-cd41c399ecb0
ms.openlocfilehash: 21dbdff63c07dbcdac8de7bf4b3a8e5d0ece7901
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784078"
---
# <a name="entity-data-model-inheritance"></a><span data-ttu-id="75c5d-102">实体数据模型：继承</span><span class="sxs-lookup"><span data-stu-id="75c5d-102">Entity Data Model: Inheritance</span></span>
<span data-ttu-id="75c5d-103">实体数据模型（EDM）支持[实体类型](entity-type.md)的继承。</span><span class="sxs-lookup"><span data-stu-id="75c5d-103">The Entity Data Model (EDM) supports inheritance for [entity types](entity-type.md).</span></span> <span data-ttu-id="75c5d-104">EDM 中的继承与面向对象的编程语言中的类的继承类似。</span><span class="sxs-lookup"><span data-stu-id="75c5d-104">Inheritance in the EDM is similar to inheritance for classes in object-oriented programming languages.</span></span> <span data-ttu-id="75c5d-105">与面向对象的语言中的类一样，在概念模型中，您可以定义从另一个实体类型（*基类型*）继承的实体类型（*派生类型*）。</span><span class="sxs-lookup"><span data-stu-id="75c5d-105">Like with classes in object-oriented languages, in a conceptual model you can define an entity type (a *derived type*) that inherits from another entity type (the *base type*).</span></span> <span data-ttu-id="75c5d-106">但是，与面向对象编程中的类不同，在概念模型中，派生类型始终继承基类型的所有[属性](property.md)和[导航属性](navigation-property.md)。</span><span class="sxs-lookup"><span data-stu-id="75c5d-106">However, unlike classes in object-oriented programming, in a conceptual model the derived type always inherits all the [properties](property.md) and [navigation properties](navigation-property.md) of the base type.</span></span> <span data-ttu-id="75c5d-107">不能重写派生类型中的继承属性。</span><span class="sxs-lookup"><span data-stu-id="75c5d-107">You cannot override inherited properties in a derived type.</span></span>  
  
 <span data-ttu-id="75c5d-108">在概念模型中，可以构建继承层次结构，其中一个派生类型将继承自另一个派生类型。</span><span class="sxs-lookup"><span data-stu-id="75c5d-108">In a conceptual model you can build inheritance hierarchies in which a derived type inherits from another derived type.</span></span> <span data-ttu-id="75c5d-109">层次结构顶部的类型（层次结构中不是派生类型的类型）称为*根类型*。</span><span class="sxs-lookup"><span data-stu-id="75c5d-109">The type at the top of the hierarchy (the one type in the hierarchy that is not a derived type) is called the *root type*.</span></span> <span data-ttu-id="75c5d-110">在继承层次结构中，必须在根类型上定义[实体键](entity-key.md)。</span><span class="sxs-lookup"><span data-stu-id="75c5d-110">In an inheritance hierarchy, the [entity key](entity-key.md) must be defined on the root type.</span></span>  
  
 <span data-ttu-id="75c5d-111">不能构建这样的继承层次结构，即一个派生类型继承自多个类型。</span><span class="sxs-lookup"><span data-stu-id="75c5d-111">You cannot build inheritance hierarchies in which a derived type inherits from more than one type.</span></span> <span data-ttu-id="75c5d-112">例如，在包含 `Book` 实体类型的概念模型中，可以定义都是继承自 `FictionBook` 的派生类型 `NonFictionBook` 和 `Book`。</span><span class="sxs-lookup"><span data-stu-id="75c5d-112">For example, in a conceptual model with a `Book` entity type, you could define derived types `FictionBook` and `NonFictionBook` that each inherit from `Book`.</span></span> <span data-ttu-id="75c5d-113">但是，随后不能定义同时继承自 `FictionBook` 和 `NonFictionBook` 类型的类型。</span><span class="sxs-lookup"><span data-stu-id="75c5d-113">However, you could not then define a type that inherits from both the `FictionBook` and `NonFictionBook` types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75c5d-114">示例</span><span class="sxs-lookup"><span data-stu-id="75c5d-114">Example</span></span>  

<span data-ttu-id="75c5d-115">下图显示了一个具有四个实体类型的概念`Book`模型`FictionBook`： `Publisher`、、 `Author`和。</span><span class="sxs-lookup"><span data-stu-id="75c5d-115">The following diagram shows a conceptual model with four entity types: `Book`, `FictionBook`, `Publisher`, and `Author`.</span></span> <span data-ttu-id="75c5d-116">`FictionBook` 实体类型是一个派生类型，继承自 `Book` 实体类型。</span><span class="sxs-lookup"><span data-stu-id="75c5d-116">The `FictionBook` entity type is a derived type, inheriting from the `Book` entity type.</span></span> <span data-ttu-id="75c5d-117">`FictionBook` 类型继承了 `ISBN (Key)`、`Title` 和 `Revision` 属性，并定义了一个名为 `Genre` 的附加属性。</span><span class="sxs-lookup"><span data-stu-id="75c5d-117">The `FictionBook` type inherits the `ISBN (Key)`, `Title`, and `Revision` properties, and defines an additional property called `Genre`.</span></span>  
  
 ![显示具有四个实体类型的概念模型的关系图。](./media/entity-data-model-inheritance/entity-type-inheritance.gif)  
  
 <span data-ttu-id="75c5d-119">[ADO.NET 实体框架](./ef/index.md)使用一种称为概念架构定义语言（[CSDL](./ef/language-reference/csdl-specification.md)）的域特定语言（DSL）来定义概念模型。</span><span class="sxs-lookup"><span data-stu-id="75c5d-119">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](./ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="75c5d-120">下面的 CSDL 定义了一个实体类型 `FictionBook`，它继承自 `Book` 类型（如上图中所示）：</span><span class="sxs-lookup"><span data-stu-id="75c5d-120">The following CSDL defines an entity type, `FictionBook`, that inherits from the `Book` type (as in the diagram above):</span></span>  
  
 [!code-xml[EDM_Example_Model#DerivedType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books5.edmx#derivedtype)]  
  
## <a name="see-also"></a><span data-ttu-id="75c5d-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="75c5d-121">See also</span></span>

- [<span data-ttu-id="75c5d-122">实体数据模型关键概念</span><span class="sxs-lookup"><span data-stu-id="75c5d-122">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="75c5d-123">实体数据模型</span><span class="sxs-lookup"><span data-stu-id="75c5d-123">Entity Data Model</span></span>](entity-data-model.md)
