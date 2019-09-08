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
# <a name="association-end-multiplicity"></a>关联端重数
*关联 end 多重性*定义可以位于[关联](association-type.md)一端的[实体类型](entity-type.md)实例的数量。  
  
 关联端重数可以具有下列值之一：  
  
- 一（1）：指示在关联端刚好存在一个实体类型实例。  
  
- 零或一（0 .. 1）：指示关联端存在零个或一个实体类型实例。  
  
- 多（\*）：指示在关联端存在零个、一个或多个实体类型实例。  
  
 关联的特征通常由关联端重数表示。 例如，如果关联端的重数为（1）和多（\*），则关联称为一对多关联。 在下面的示例中，`PublishedBy` 关联是一个一对多关联（一个出版商可以出版很多书，而一本书只能由一个出版商出版）。 `WrittenBy` 关联是一个多对多关联（一本书可以有多位作者，而一位作者可以著有多本书）。  
  
## <a name="example"></a>示例  
 下图显示了一个具有两个关联的概念模型：`PublishedBy` 和 `WrittenBy`。 `PublishedBy` 关联的关联端是 `Book` 和 `Publisher` 实体类型。 `Publisher` End 的重数为一（1），而`Book`末尾的重数为 many （\*）。  
  
 ![具有三个实体类型的示例模型](./media/association-end-multiplicity/example-model-three-entity-types.gif)  
  
 ADO.NET 实体框架使用一种称为概念架构定义语言（[CSDL](./ef/language-reference/csdl-specification.md)）的域特定语言（DSL）来定义概念模型。 下面的 CSDL 定义了上图中显示的 `PublishedBy` 关联：  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>请参阅

- [实体数据模型关键概念](entity-data-model-key-concepts.md)
- [实体数据模型](entity-data-model.md)
