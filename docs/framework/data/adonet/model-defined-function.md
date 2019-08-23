---
title: 模型定义函数
ms.date: 03/30/2017
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
ms.openlocfilehash: 05a44e86a118b649490cde849c8ca2c2bb0d2f15
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934525"
---
# <a name="model-defined-function"></a>模型定义函数
*模型定义的函数*是在概念模型中定义的函数。 模型定义函数的主体以[实体 SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)表示, 这允许独立于数据源中支持的规则或语言来表示函数。  
  
 模型定义函数的定义包含以下信息：  
  
- 函数名。 （必需）  
  
- 返回值的类型。 （可选）  
  
    > [!NOTE]
    > 如果未指定返回类型，则返回值为 void。  
  
- 参数信息。 （可选）  
  
- 定义函数主体的[实体 SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)表达式。  
  
 请注意，模型定义函数不支持输出参数。 这一限制可以保证无法对模型定义函数进行编写。  
  
## <a name="example"></a>示例  
 下图显示了一个具有三个实体类型的概念模型：`Book`、`Publisher` 和 `Author`。  
  
 ![显示具有发布日期的模型的屏幕截图。](./media/model-defined-function/model-published-date-three-entity-types.gif)  
  
 [ADO.NET 实体框架](../../../../docs/framework/data/adonet/ef/index.md)使用一种称为概念架构定义语言 ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) 的域特定语言 (DSL) 来定义概念模型。 下面的 CSDL 在概念模型中定义了一个函数，它返回自某个 `Book` 实例（如上图所示）出版以来的年数。  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a>请参阅

- [实体数据模型关键概念](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [实体数据模型](../../../../docs/framework/data/adonet/entity-data-model.md)
- [实体数据模型:基元数据类型](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)
