---
title: 实体数据模型
ms.date: 03/30/2017
ms.assetid: 2dda3d5b-4582-4ba0-a91d-fcd7a1498137
ms.openlocfilehash: e76527b497434ada06762fcab931522fffa2a16b
ms.sourcegitcommit: ad99773e5e45068ce03b99518008397e1299e0d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2018
ms.locfileid: "46577238"
---
# <a name="entity-data-model"></a><span data-ttu-id="04f7d-102">实体数据模型</span><span class="sxs-lookup"><span data-stu-id="04f7d-102">Entity Data Model</span></span>
<span data-ttu-id="04f7d-103">实体数据模型 (EDM) 是一组描述数据结构（而不管其存储形式如何）的概念。</span><span class="sxs-lookup"><span data-stu-id="04f7d-103">The Entity Data Model (EDM) is a set of concepts that describe the structure of data, regardless of its stored form.</span></span> <span data-ttu-id="04f7d-104">EDM 借自于 Peter Chen 于 1976 年所描述的实体关系模型，但它是在实体关系模型基础上构建的并扩展了其传统用途。</span><span class="sxs-lookup"><span data-stu-id="04f7d-104">The EDM borrows from the Entity-Relationship Model described by Peter Chen in 1976, but it also builds on the Entity-Relationship Model and extends its traditional uses.</span></span>  
  
 <span data-ttu-id="04f7d-105">EDM 解决了以多种形式存储的数据所带来的难题。</span><span class="sxs-lookup"><span data-stu-id="04f7d-105">The EDM addresses the challenges that arise from having data stored in many forms.</span></span> <span data-ttu-id="04f7d-106">例如，假设某项业务将数据存储在关系数据库、文本文件、XML 文件、电子表格和报表中。</span><span class="sxs-lookup"><span data-stu-id="04f7d-106">For example, consider a business that stores data in relational databases, text files, XML files, spreadsheets, and reports.</span></span> <span data-ttu-id="04f7d-107">这在数据建模、应用程序设计和数据访问方面会带来很大的难题。</span><span class="sxs-lookup"><span data-stu-id="04f7d-107">This presents significant challenges in data modeling, application design, and data access.</span></span> <span data-ttu-id="04f7d-108">当设计面向对象的应用程序时，其困难在于如何编写高效的、可维护的代码而不必牺牲数据访问、存储和可扩展性方面的高效性。</span><span class="sxs-lookup"><span data-stu-id="04f7d-108">When designing a data-oriented application, the challenge is to write efficient and maintainable code without sacrificing efficient data access, storage, and scalability.</span></span> <span data-ttu-id="04f7d-109">当数据具有关系结构时，其在数据访问、存储和可扩展性方面会非常高效，但编写高效的、可维护的代码则变得非常困难。</span><span class="sxs-lookup"><span data-stu-id="04f7d-109">When data has a relational structure, data access, storage, and scalability are very efficient, but writing efficient and maintainable code becomes more difficult.</span></span> <span data-ttu-id="04f7d-110">当数据具有对象结构时，上述关系恰好相反：编写高效的、可维护的代码要以牺牲数据访问、存储和可扩展性方面的高效性为代价。</span><span class="sxs-lookup"><span data-stu-id="04f7d-110">When data has an object structure, the trade-offs are reversed: Writing efficient and maintainable code comes at the cost of efficient data access, storage, and scalability.</span></span> <span data-ttu-id="04f7d-111">即使可以在这些优劣方面找到最佳平衡，但是当将数据从一种形式转变为另一种形式时又会引发新的难题。</span><span class="sxs-lookup"><span data-stu-id="04f7d-111">Even if the right balance between these trade-offs can be found, new challenges arise when data is moved from one form to another.</span></span> <span data-ttu-id="04f7d-112">实体数据模型通过以独立于任何存储架构的实体和关系的方式描述数据结构解决了这些难题。</span><span class="sxs-lookup"><span data-stu-id="04f7d-112">The Entity Data Model addresses these challenges by describing the structure of data in terms of entities and relationships that are independent of any storage schema.</span></span> <span data-ttu-id="04f7d-113">这使得数据的存储形式与应用程序设计和开发变得不相关。</span><span class="sxs-lookup"><span data-stu-id="04f7d-113">This makes the stored form of data irrelevant to application design and development.</span></span> <span data-ttu-id="04f7d-114">此外，由于实体和关系描述的是数据在应用程序中使用时的结构（而不是其存储形式），因此它们会随应用程序的演变而演变。</span><span class="sxs-lookup"><span data-stu-id="04f7d-114">And, because entities and relationships describe the structure of data as it is used in an application (not its stored form), they can evolve as an application evolves.</span></span>  
  
 <span data-ttu-id="04f7d-115">`conceptual model`是实体和关系的数据结构的特定表示形式，通常用实现 EDM 概念的域特定语言 (DSL) 定义。</span><span class="sxs-lookup"><span data-stu-id="04f7d-115">A `conceptual model` is a specific representation of the structure of data as entities and relationships, and is generally defined in a domain-specific language (DSL) that implements the concepts of the EDM.</span></span> <span data-ttu-id="04f7d-116">[概念架构定义语言 (CSDL)](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)是这种域特定语言的示例。</span><span class="sxs-lookup"><span data-stu-id="04f7d-116">[Conceptual schema definition language (CSDL)](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md) is an example of such a domain-specific language.</span></span> <span data-ttu-id="04f7d-117">可以将概念模型中描述的实体和关系视为对应用程序中的对象和关联的一种抽象表述。</span><span class="sxs-lookup"><span data-stu-id="04f7d-117">Entities and relationships described in a conceptual model can be thought of as abstractions of objects and associations in an application.</span></span> <span data-ttu-id="04f7d-118">这使得开发人员可以专注于概念模型而不必考虑存储架构，从而在编写代码时更多关注高效性和可维护性。</span><span class="sxs-lookup"><span data-stu-id="04f7d-118">This allows developers to focus on the conceptual model without concern for the storage schema, and allows them to write code with efficiency and maintainability in mind.</span></span> <span data-ttu-id="04f7d-119">与此同时，存储架构设计者可以专注于数据访问、存储和可扩展性方面的高效性。</span><span class="sxs-lookup"><span data-stu-id="04f7d-119">Meanwhile storage schema designers can focus on the efficiency of data access, storage, and scalability.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="04f7d-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="04f7d-120">In This Section</span></span>  
 <span data-ttu-id="04f7d-121">本节中的主题描述实体数据模型的概念。</span><span class="sxs-lookup"><span data-stu-id="04f7d-121">Topics in this section describe the concepts of the Entity Data Model.</span></span> <span data-ttu-id="04f7d-122">实现 EDM 的任何 DSL 都应包含这里描述的概念。</span><span class="sxs-lookup"><span data-stu-id="04f7d-122">Any DSL that implements the EDM should include the concepts described here.</span></span> <span data-ttu-id="04f7d-123">请注意， [ADO.NET 实体框架](../../../../docs/framework/data/adonet/ef/index.md)使用 CSDL 来定义概念模型。</span><span class="sxs-lookup"><span data-stu-id="04f7d-123">Note that the [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses CSDL to define conceptual models.</span></span> <span data-ttu-id="04f7d-124">有关详细信息，请参阅[CSDL 规范](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)。</span><span class="sxs-lookup"><span data-stu-id="04f7d-124">For more information, see [CSDL Specification](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).</span></span>  
  
 [<span data-ttu-id="04f7d-125">实体数据模型关键概念</span><span class="sxs-lookup"><span data-stu-id="04f7d-125">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
  
 [<span data-ttu-id="04f7d-126">实体数据模型：命名空间</span><span class="sxs-lookup"><span data-stu-id="04f7d-126">Entity Data Model: Namespaces</span></span>](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md)  
  
 [<span data-ttu-id="04f7d-127">实体数据模型：基元数据类型</span><span class="sxs-lookup"><span data-stu-id="04f7d-127">Entity Data Model: Primitive Data Types</span></span>](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)  
  
 [<span data-ttu-id="04f7d-128">实体数据模型：继承</span><span class="sxs-lookup"><span data-stu-id="04f7d-128">Entity Data Model: Inheritance</span></span>](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md)  
  
 [<span data-ttu-id="04f7d-129">关联端</span><span class="sxs-lookup"><span data-stu-id="04f7d-129">association end</span></span>](../../../../docs/framework/data/adonet/association-end.md)  
  
 [<span data-ttu-id="04f7d-130">关联端重数</span><span class="sxs-lookup"><span data-stu-id="04f7d-130">association end multiplicity</span></span>](../../../../docs/framework/data/adonet/association-end-multiplicity.md)  
  
 [<span data-ttu-id="04f7d-131">关联集</span><span class="sxs-lookup"><span data-stu-id="04f7d-131">association set</span></span>](../../../../docs/framework/data/adonet/association-set.md)  
  
 [<span data-ttu-id="04f7d-132">关联集端</span><span class="sxs-lookup"><span data-stu-id="04f7d-132">association set end</span></span>](../../../../docs/framework/data/adonet/association-set-end.md)  
  
 [<span data-ttu-id="04f7d-133">关联类型</span><span class="sxs-lookup"><span data-stu-id="04f7d-133">association type</span></span>](../../../../docs/framework/data/adonet/association-type.md)  
  
 [<span data-ttu-id="04f7d-134">复杂类型</span><span class="sxs-lookup"><span data-stu-id="04f7d-134">complex type</span></span>](../../../../docs/framework/data/adonet/complex-type.md)  
  
 [<span data-ttu-id="04f7d-135">实体容器</span><span class="sxs-lookup"><span data-stu-id="04f7d-135">entity container</span></span>](../../../../docs/framework/data/adonet/entity-container.md)  
  
 [<span data-ttu-id="04f7d-136">实体键</span><span class="sxs-lookup"><span data-stu-id="04f7d-136">entity key</span></span>](../../../../docs/framework/data/adonet/entity-key.md)  
  
 [<span data-ttu-id="04f7d-137">实体集</span><span class="sxs-lookup"><span data-stu-id="04f7d-137">entity set</span></span>](../../../../docs/framework/data/adonet/entity-set.md)  
  
 [<span data-ttu-id="04f7d-138">实体类型</span><span class="sxs-lookup"><span data-stu-id="04f7d-138">entity type</span></span>](../../../../docs/framework/data/adonet/entity-type.md)  
  
 [<span data-ttu-id="04f7d-139">facet</span><span class="sxs-lookup"><span data-stu-id="04f7d-139">facet</span></span>](../../../../docs/framework/data/adonet/facet.md)  
  
 [<span data-ttu-id="04f7d-140">外键属性</span><span class="sxs-lookup"><span data-stu-id="04f7d-140">foreign key property</span></span>](../../../../docs/framework/data/adonet/foreign-key-property.md)  
  
 [<span data-ttu-id="04f7d-141">模型声明函数</span><span class="sxs-lookup"><span data-stu-id="04f7d-141">model-declared function</span></span>](../../../../docs/framework/data/adonet/model-declared-function.md)  
  
 [<span data-ttu-id="04f7d-142">模型定义函数</span><span class="sxs-lookup"><span data-stu-id="04f7d-142">model-defined function</span></span>](../../../../docs/framework/data/adonet/model-defined-function.md)  
  
 [<span data-ttu-id="04f7d-143">导航属性</span><span class="sxs-lookup"><span data-stu-id="04f7d-143">navigation property</span></span>](../../../../docs/framework/data/adonet/navigation-property.md)  
  
 [<span data-ttu-id="04f7d-144">属性</span><span class="sxs-lookup"><span data-stu-id="04f7d-144">property</span></span>](../../../../docs/framework/data/adonet/property.md)  
  
 [<span data-ttu-id="04f7d-145">引用完整性约束</span><span class="sxs-lookup"><span data-stu-id="04f7d-145">referential integrity constraint</span></span>](../../../../docs/framework/data/adonet/referential-integrity-constraint.md)  
  
## <a name="see-also"></a><span data-ttu-id="04f7d-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="04f7d-146">See Also</span></span>  
 [<span data-ttu-id="04f7d-147">ADO.NET 实体数据模型工具</span><span class="sxs-lookup"><span data-stu-id="04f7d-147">ADO.NET Entity Data Model  Tools</span></span>](https://msdn.microsoft.com/library/91076853-0881-421b-837a-f582f36be527)  
 [<span data-ttu-id="04f7d-148">.edmx 文件概述</span><span class="sxs-lookup"><span data-stu-id="04f7d-148">.edmx File Overview</span></span>](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)  
 [<span data-ttu-id="04f7d-149">CSDL 规范</span><span class="sxs-lookup"><span data-stu-id="04f7d-149">CSDL Specification</span></span>](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)
