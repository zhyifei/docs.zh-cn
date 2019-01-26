---
title: 外键属性
ms.date: 03/30/2017
ms.assetid: 23cb6729-544d-4f67-9ee7-44e8a6545587
ms.openlocfilehash: a33d60e28c7c4e5a90199437fc95a83b5a304b06
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54746604"
---
# <a name="foreign-key-property"></a>外键属性
一个*外键属性*实体数据模型 (EDM) 中是基元类型[属性](../../../../docs/framework/data/adonet/property.md)（或一组基元类型属性） 上[实体类型](../../../../docs/framework/data/adonet/entity-type.md)，其中包含[实体键](../../../../docs/framework/data/adonet/entity-key.md)的另一个实体类型。  
  
 外键属性相当于关系数据库中的外键列。 在关系数据库中使用外键列是表中的行之间创建关系的相同方式，在概念模型中的外键属性用于建立[关联](../../../../docs/framework/data/adonet/association-type.md)实体类型之间。 一个[引用完整性约束](../../../../docs/framework/data/adonet/referential-integrity-constraint.md)用于定义一种类型具有外键属性时的两个实体类型之间的关联。  
  
## <a name="example"></a>示例  
 下图显示了一个具有三个实体类型的概念模型：`Book`、`Publisher` 和 `Author`。 `Book` 实体类型有一个属性 `PublisherId`，当您为 `Publisher` 关联定义一个引用完整性约束时，它将引用 `PublishedBy` 实体类型的实体键。  
  
 ![RefConstraintModel](../../../../docs/framework/data/adonet/media/refconstraintmodel.gif "RefConstraintModel")  
  
 [ADO.NET 实体框架](../../../../docs/framework/data/adonet/ef/index.md)使用称为概念性架构定义语言的特定于域的语言 (DSL) ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 来定义概念模型。 下面的 CSDL 使用外键属性 `PublisherId` 为上图所示的概念模型中的 `PublishedBy` 关联定义了一个引用完整性约束。  
  
 [!code-xml[EDM_Example_Model#RefConstraint](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#refconstraint)]  
  
## <a name="see-also"></a>请参阅
- [实体数据模型关键概念](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [实体数据模型](../../../../docs/framework/data/adonet/entity-data-model.md)
