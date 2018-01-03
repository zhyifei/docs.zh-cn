---
title: "Association Set — 关联集"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a65247b6-ce59-44ea-974c-14ae20a7995f
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 5be982d25a4ab135d2b521b558e809b306b88230
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="association-set"></a>Association Set — 关联集
*关联集*是的逻辑容器[关联](../../../../docs/framework/data/adonet/association-type.md)相同类型的实例。 关联集不是一种数据建模构造，也就是说，它没有描述数据结构或关系。 相反，关联集提供了一种承载或存储环境构造（例如公共语言运行库或 SQL Server 数据库）来分组关联实例，以便可以将它们映射到某个数据存储区。  
  
 关联集定义中[实体容器](../../../../docs/framework/data/adonet/entity-container.md)，即的逻辑分组[实体集](../../../../docs/framework/data/adonet/entity-set.md)和关联集。  
  
 关联集的定义包含以下信息：  
  
-   关联集名称。 （必需）  
  
-   要包含其实例的关联。 （必需）  
  
-   两个[关联集端](../../../../docs/framework/data/adonet/association-set-end.md)。  
  
## <a name="example"></a>示例  
 下图显示了一个具有两个关联的概念模型：`PublishedBy` 和 `WrittenBy`。 上图没有传达有关关联集的信息，但下图显示了一个基于此模型的关联集和实体集的示例。  
  
 ![示例模型](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 下面的示例显示了基于上面所示的概念模型的一个关联集 (`PublishedBy`) 和两个实体集（`Books` 和 `Publishers`）。 在 bi`Books`实体集表示的实例`Book`在运行时的实体类型。 同样，Pj 表示`Publisher`实例中`Publishers`实体集。 BiPj 表示的实例`PublishedBy`中的关联`PublishedBy`关联集。  
  
 ![设置示例](../../../../docs/framework/data/adonet/media/setsexample.gif "SetsExample")  
  
 [ADO.NET 实体框架](../../../../docs/framework/data/adonet/ef/index.md)使用域特定语言 (DSL) 称为概念架构定义语言 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 来定义概念模型。 下面的 CSDL 定义了一个实体容器，其中对于上图所示的每个关联都有一个关联集。 请注意，每个关联集的名称和关联都是使用 XML 特性定义的。  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 可以定义每个关联，只要没有两个关联集共享的多个关联集[关联集端](../../../../docs/framework/data/adonet/association-set-end.md)。 下面的 CSDL 定义了一个实体容器，其中包含 `WrittenBy` 关联的两个关联集。 请注意，为 `Book` 和 `Author` 实体类型定义了多个实体集，并且没有关联集共享关联集端。  
  
 [!code-xml[EDM_Example_Model#MultipleAssociationSets](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#multipleassociationsets)]  
  
## <a name="see-also"></a>请参阅  
 [实体数据模型关键概念](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [实体数据模型](../../../../docs/framework/data/adonet/entity-data-model.md)  
 [外键属性](../../../../docs/framework/data/adonet/foreign-key-property.md)
