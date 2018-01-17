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
ms.workload: dotnet
ms.openlocfilehash: 421a2bdbf2652880097fb1df3c9b63f38ac2bd10
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="entity-data-model-inheritance"></a>实体数据模型：继承
实体数据模型 (EDM) 支持的继承[实体类型](../../../../docs/framework/data/adonet/entity-type.md)。 EDM 中的继承与面向对象的编程语言中的类的继承类似。 像使用面向对象的语言中的类，在概念模型中可定义一个实体类型 (*派生类型*)，继承自另一个实体类型 (*基类型*)。 但是，与面向对象编程中的类，不同的概念模型中的派生的类型始终会继承所有[属性](../../../../docs/framework/data/adonet/property.md)和[导航属性](../../../../docs/framework/data/adonet/navigation-property.md)的基类型。 不能重写派生类型中的继承属性。  
  
 在概念模型中，可以构建继承层次结构，其中一个派生类型将继承自另一个派生类型。 在层次结构 （不是派生的类型的层次结构中的一个类型） 的顶部的类型称为*根类型*。 继承层次结构，在[实体键](../../../../docs/framework/data/adonet/entity-key.md)必须在根类型上定义。  
  
 不能构建这样的继承层次结构，即一个派生类型继承自多个类型。 例如，在包含 `Book` 实体类型的概念模型中，可以定义都是继承自 `FictionBook` 的派生类型 `NonFictionBook` 和 `Book`。 但是，随后不能定义同时继承自 `FictionBook` 和 `NonFictionBook` 类型的类型。  
  
## <a name="example"></a>示例  
 下图显示了一个具有四个实体类型的概念模型：`Book`、`FictionBook`、`Publisher` 和 `Author`。 `FictionBook` 实体类型是一个派生类型，继承自 `Book` 实体类型。 `FictionBook` 类型继承了 `ISBN (Key)`、`Title` 和 `Revision` 属性，并定义了一个名为 `Genre` 的附加属性。  
  
 ![继承](../../../../docs/framework/data/adonet/media/inheritanceexample.gif "InheritanceExample")  
  
 [ADO.NET 实体框架](../../../../docs/framework/data/adonet/ef/index.md)使用域特定语言 (DSL) 称为概念架构定义语言 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 来定义概念模型。 下面的 CSDL 定义了一个实体类型 `FictionBook`，它继承自 `Book` 类型（如上图中所示）：  
  
 [!code-xml[EDM_Example_Model#DerivedType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books5.edmx#derivedtype)]  
  
## <a name="see-also"></a>请参阅  
 [实体数据模型关键概念](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [实体数据模型](../../../../docs/framework/data/adonet/entity-data-model.md)
