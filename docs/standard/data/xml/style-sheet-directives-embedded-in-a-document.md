---
title: "嵌入到文档中的样式表指令"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d79fb295-ebc7-438d-ba1b-05be7d534834
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8c5cfcc9f35e4a07e9426a4dd24c1e2f04985f16
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="style-sheet-directives-embedded-in-a-document"></a>嵌入到文档中的样式表指令
有时，现有 XML 会包含 `<?xml:stylesheet?>` 形式的样式表指令。 作为替代方法的 Microsoft Internet Explorer 接受此`<?xml-stylesheet?>`语法。 当 XML 数据包含 `<?xml:stylesheet?>` 指令时（如下面的数据所示），试图将此数据加载到 XML 文档对象模型 (DOM) 中将引发异常。  
  
```xml  
<?xml version="1.0" ?>  
<?xml:stylesheet type="text/xsl" href="test2.xsl"?>  
<root>  
    <test>Node 1</test>  
    <test>Node 2</test>  
</root>  
```  
  
 这是因为`<?xml:stylesheet?>`被视为无效**ProcessingInstruction** dom 任何**ProcessingInstruction**，根据 XML 规范中的命名空间，只能是无冒号名称 (NCNames)，与限定名 (QNames)。  
  
 从 XML 规范，个的效果中的命名空间的第 6 节**负载**和**LoadXml**方法符合该规范是，在文档中：  
  
-   所有元素类型和属性名都包含零个或一个冒号。  
  
-   任何实体名称、ProcessingInstruction 目标或表示法名称都不包含冒号。  
  
 因为 `<?xml:stylesheet?>` 包含一个冒号，所以您违反了第二条规则。  
  
 根据万维网联合会 (W3C) 将样式表与 XML 文档关联的 1.0 版建议（位于 www.w3.org/TR/xml-stylesheet），将 XSL 样式表与 XML 文档关联的处理指令是 `<?xml-stylesheet?>`（用短划线代替冒号）。  
  
## <a name="see-also"></a>另请参阅  
 [XML 文档对象模型 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
