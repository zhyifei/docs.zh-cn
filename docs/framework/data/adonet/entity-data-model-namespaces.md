---
title: "实体数据模型：命名空间"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98ab4226-bb9f-44e7-af46-61a9b1a4e47c
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: b3e69017b5f617cff9bf2c159d5538a8c41e4cc0
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
---
# <a name="entity-data-model-namespaces"></a><span data-ttu-id="d1d8f-102">实体数据模型：命名空间</span><span class="sxs-lookup"><span data-stu-id="d1d8f-102">Entity Data Model: Namespaces</span></span>
<span data-ttu-id="d1d8f-103">实体数据模型 (EDM) 中的命名空间是用于的抽象容器[实体类型](../../../../docs/framework/data/adonet/entity-type.md)，[复杂类型](../../../../docs/framework/data/adonet/complex-type.md)，和[关联](../../../../docs/framework/data/adonet/association-type.md)。</span><span class="sxs-lookup"><span data-stu-id="d1d8f-103">A namespace in the Entity Data Model (EDM) is an abstract container for [entity types](../../../../docs/framework/data/adonet/entity-type.md), [complex types](../../../../docs/framework/data/adonet/complex-type.md), and [associations](../../../../docs/framework/data/adonet/association-type.md).</span></span> <span data-ttu-id="d1d8f-104">EDM 中的命名空间类似于编程语言中的命名空间：它们为自己所包含的对象提供了上下文，并为消除具有相同名称（但包含在不同的命名空间中）的对象的歧义提供了一种方式。</span><span class="sxs-lookup"><span data-stu-id="d1d8f-104">Namespaces in the EDM are similar to namespaces in a programming language: they provide context for the objects that they contain and they provide a way to disambiguate objects that have the same name (but are contained in different namespaces).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1d8f-105">示例</span><span class="sxs-lookup"><span data-stu-id="d1d8f-105">Example</span></span>  
 <span data-ttu-id="d1d8f-106">[ADO.NET 实体框架](../../../../docs/framework/data/adonet/ef/index.md)使用域特定语言 (DSL) 称为概念架构定义语言 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 来定义概念模型。</span><span class="sxs-lookup"><span data-stu-id="d1d8f-106">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="d1d8f-107">下面的 CSDL 代码使用命名空间来标识一个在不同概念模型中定义的类型。</span><span class="sxs-lookup"><span data-stu-id="d1d8f-107">The following CSDL code uses a namespace to identify a type that is defined in a different conceptual model.</span></span> <span data-ttu-id="d1d8f-108">该示例定义了一个实体类型 (`Publisher`)，它有一个从 `Address` 命名空间导入的复杂类型属性 (`ExtendedBooksModel`)。</span><span class="sxs-lookup"><span data-stu-id="d1d8f-108">The example defines an entity type (`Publisher`) that has a complex type property (`Address`) that is imported from the `ExtendedBooksModel` namespace.</span></span> <span data-ttu-id="d1d8f-109">请注意，`Using` 元素表明导入了一个命名空间。</span><span class="sxs-lookup"><span data-stu-id="d1d8f-109">Note that the `Using` element indicates that a namespace has been imported.</span></span> <span data-ttu-id="d1d8f-110">还要注意的是，`Address` 属性的类型是使用其完全限定名称 (`ExtendedBooksModel.Address`) 定义的，表明该类型是在 `ExtendedBooksModel` 命名空间中定义的。</span><span class="sxs-lookup"><span data-stu-id="d1d8f-110">Also note that the type of the `Address` property is defined by using its fully qualified name (`ExtendedBooksModel.Address`), indicating that this type is defined in the `ExtendedBooksModel` namespace.</span></span>  
  
 [!code-xml[EDM_Example_Model#ImportedNamespace](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books6.edmx#importednamespace)]  
  
## <a name="see-also"></a><span data-ttu-id="d1d8f-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1d8f-111">See Also</span></span>  
 [<span data-ttu-id="d1d8f-112">实体数据模型关键概念</span><span class="sxs-lookup"><span data-stu-id="d1d8f-112">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="d1d8f-113">实体数据模型</span><span class="sxs-lookup"><span data-stu-id="d1d8f-113">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
