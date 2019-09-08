---
title: 将关键 XML 架构 (XSD) 约束映射到数据集约束
ms.date: 03/30/2017
ms.assetid: 3d0d1a4b-9104-434f-ac04-6c01ab5716b5
ms.openlocfilehash: b44c3193e1b9e2e52e086111eab0ab0b0cae5c97
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786073"
---
# <a name="mapping-xml-schema-xsd-constraints-to-dataset-constraints"></a>将关键 XML 架构 (XSD) 约束映射到数据集约束
XML 架构定义语言 (XSD) 允许对它所定义的元素和属性指定约束。 将 xml 架构映射到中<xref:System.Data.DataSet>的关系架构时，xml 架构约束将映射到**数据集中**的表和列的相应关系约束。  
  
 本节讨论以下 XML 架构约束的映射：  
  
- 使用**unique**元素指定的唯一性约束。  
  
- 使用**key**元素指定的键约束。  
  
- 使用**keyref**元素指定的 keyref 约束。  
  
 使用对元素或属性的约束，可以对任何文档实例中元素的值指定特定的限制。 例如，架构中**Customer**元素的**customerid**子元素的键约束指示**customerid**子元素的值在任何文档实例中必须唯一，并且不允许空值。  
  
 为了在文档中建立关系，也可以在文档中的元素和属性之间指定约束。 key 和 keyref 约束用于在架构中指定文档中的约束，从而生成文档元素和属性之间的关系。  
  
 映射过程将这些架构约束转换为在**数据集**内创建的表的适当约束。  
  
## <a name="in-this-section"></a>本节内容  
 [将唯一 XML 架构 (XSD) 约束映射到数据集约束](map-unique-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 介绍用于在**数据集中**创建唯一约束的 XML 架构元素。  
  
 [将关键 XML 架构 (XSD) 约束映射到数据集约束](map-key-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 介绍用于在**数据集中**创建键约束的 XML 架构元素（不允许使用 null 值的唯一约束）。  
  
 [将 keyref XML 架构 (XSD) 约束映射到数据集约束](map-keyref-xml-schema-xsd-constraints-to-dataset-constraints.md)  
 介绍用于在**数据集中**创建 keyref （外键）约束的 XML 架构元素。  
  
## <a name="related-sections"></a>相关章节  
 [从 XML 架构派生数据集关系结构 (XSD)](deriving-dataset-relational-structure-from-xml-schema-xsd.md)  
 描述从 XSD 架构创建的**数据集**的关系结构（或架构）。  
  
 [从 XML 架构生成数据集关系 (XSD)](generating-dataset-relations-from-xml-schema-xsd.md)  
 介绍用于在**数据集中**的表列之间创建关系的 XML 架构元素。  
  
## <a name="see-also"></a>请参阅

- [ADO.NET 概述](../ado-net-overview.md)
