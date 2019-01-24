---
title: Navigation Property — 导航属性
ms.date: 03/30/2017
ms.assetid: d0bf1a6a-1d84-484c-b7c3-b410fd8dc0b1
ms.openlocfilehash: 09c0e5e5dbc7b2be89e044c4d111fdd65fada7c7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54662174"
---
# <a name="navigation-property"></a>Navigation Property — 导航属性
一个*导航属性*上为可选属性[实体类型](../../../../docs/framework/data/adonet/entity-type.md)允许进行从一个导航[最终](../../../../docs/framework/data/adonet/association-end.md)的[关联](../../../../docs/framework/data/adonet/association-type.md)到另一端。 与其他不同[属性](../../../../docs/framework/data/adonet/property.md)，导航属性并不携带数据。  
  
 导航属性定义包含以下信息：  
  
-   名称。 （必需）  
  
-   导航属性要导航的关联。 （必需）  
  
-   导航属性要导航的关联端。 （必需）  
  
 注意，对于关联两端的两种实体类型，导航属性都是可选的。 如果您对于位于关联一端的实体类型定义一个导航属性，则不需要对于位于关联另一端的实体类型定义导航属性。  
  
 一个导航属性的数据类型由[多重性](../../../../docs/framework/data/adonet/association-end-multiplicity.md)的其远程[关联端](../../../../docs/framework/data/adonet/association-end.md)。 例如，假设导航属性 `OrdersNavProp` 存在于 `Customer` 实体类型上并导航 `Customer` 与 `Order` 之间的一对多关系。 因为导航属性的远程关联端的重数为多 (*)，所以其数据类型是一个集合（属于 `Order`）。 同样，如果导航属性 `CustomerNavProp` 存在于 `Order` 实体类型上，但由于远程端的重数为“一 (1)”，所以其数据类型应为 `Customer`。  
  
## <a name="example"></a>示例  
 下图显示了一个具有三个实体类型的概念模型：`Book`、`Publisher` 和 `Author`。 导航属性 `Publisher` 和 `Authors` 都是在 Book 实体类型上定义的。 导航属性 `Books` 是同时在 Publisher 实体类型和 `Author` 实体类型上定义的。  
  
 ![具有导航属性的模型](../../../../docs/framework/data/adonet/media/modelwithnavprops.gif "ModelWithNavProps")  
  
 [ADO.NET 实体框架](../../../../docs/framework/data/adonet/ef/index.md)使用称为概念性架构定义语言的特定于域的语言 (DSL) ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 来定义概念模型。 下面的 CSDL 定义了上图中显示的 `Book` 实体类型。  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 请注意，XML 特性用于传达定义导航属性所需信息：该属性`Name`包含的属性名称`Relationship`包含它导航时，关联的名称和`FromRole`和`ToRole`包含关联的两端。  
  
## <a name="see-also"></a>请参阅
- [实体数据模型关键概念](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [实体数据模型](../../../../docs/framework/data/adonet/entity-data-model.md)
