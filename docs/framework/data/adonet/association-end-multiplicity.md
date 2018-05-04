---
title: 关联端重数
ms.date: 03/30/2017
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
ms.openlocfilehash: 2f70fa4b163b957ea1e43506033863c3540b0418
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="association-end-multiplicity"></a>关联端重数
*关联端重数*定义数[实体类型](../../../../docs/framework/data/adonet/entity-type.md)的一端可以存在的实例[关联](../../../../docs/framework/data/adonet/association-type.md)。  
  
 关联端重数可以具有下列值之一：  
  
-   一 (1)：表明在关联端存在且只存在一个实体类型实例。  
  
-   零或一 (0..1)：表明在关联端不存在实体类型实例或存在一个实体类型实例。  
  
-   多 (*)：表明在关联端不存在实体类型实例，或者存在一个或多个实体类型实例。  
  
 关联的特征通常由关联端重数表示。 例如，如果某个关联的两端的重数分别为“一 (1)”和“多 (*)”，则该关联称为一对多关联。 在下面的示例中，`PublishedBy` 关联是一个一对多关联（一个出版商可以出版很多书，而一本书只能由一个出版商出版）。 `WrittenBy` 关联是一个多对多关联（一本书可以有多位作者，而一位作者可以著有多本书）。  
  
## <a name="example"></a>示例  
 下图显示了一个具有两个关联的概念模型：`PublishedBy` 和 `WrittenBy`。 `PublishedBy` 关联的关联端是 `Book` 和 `Publisher` 实体类型。 `Publisher` 端的重数为“一 (1)”，`Book` 端的重数为“多 (*)”。  
  
 ![示例模型](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 ADO.NET 实体框架使用的域特定语言 (DSL) 称为概念架构定义语言 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 来定义概念模型。 下面的 CSDL 定义了上图中显示的 `PublishedBy` 关联：  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>请参阅  
 [实体数据模型关键概念](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [实体数据模型](../../../../docs/framework/data/adonet/entity-data-model.md)
