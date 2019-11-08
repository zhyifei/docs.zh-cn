---
title: 关联集端
ms.date: 03/30/2017
ms.assetid: fe4bf1d3-047a-4a37-98c5-a66e70811346
ms.openlocfilehash: f7ec1ca6fcdf299b9fcfc78f299ea4c6c5267cd3
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738627"
---
# <a name="association-set-end"></a>关联集端
*关联集端*在[关联集](association-set.md)的末尾标识[实体类型](entity-type.md)和[实体集](entity-set.md)。 关联集端定义为关联集的一部分；一个关联集必须有且只有两个关联集端。  
  
 关联集端定义包含以下信息：  
  
- 关联集中涉及的实体类型之一。 （必需）  
  
- 关联集中涉及的实体类型的实体集。 （必需）  
  
## <a name="example"></a>示例  
 下图显示了一个具有两个关联的概念模型：`WrittenBy` 和 `PublishedBy`。  
  
 ![具有三个实体类型的示例模型](./media/association-set-end/example-model-three-entity-types.gif)  
  
 下图显示了基于上面所示的概念模型的一个关联集 (`PublishedBy`) 和两个实体集（`Books` 和 `Publishers`）。 关联集端是 `Books` 和 `Publishers` 实体集。 `Books` 实体集中的 Bi 表示运行时 `Book` 实体类型的实例。 同样，Pj 表示 `Publishers` 实体集中的 `Publisher` 实例。 BiPj 表示 `PublishedBy` 关联集中 `PublishedBy` 关联的实例。  
  
 ![显示集合示例的屏幕截图。](./media/association-set-end/sets-example-association.gif)  
  
 [ADO.NET 实体框架](./ef/index.md)使用称为概念架构定义语言（[CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)）的 DSL 来定义概念模型。 下面的 CSDL 定义了一个实体容器，其中对于上图所示的每个关联都有一个关联集。 请注意，关联集端定义为每个关联集定义的一部分。  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
## <a name="see-also"></a>请参阅

- [实体数据模型关键概念](entity-data-model-key-concepts.md)
- [实体数据模型](entity-data-model.md)
