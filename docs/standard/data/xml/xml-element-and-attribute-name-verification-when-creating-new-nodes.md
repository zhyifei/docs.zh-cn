---
title: "创建新节点时的 XML 元素和属性名验证"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c041d5d2830222f3fae09a39f1ea10eb08772388
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a>创建新节点时的 XML 元素和属性名验证
XML 文档对象模型 (DOM) 在创建新元素节点或属性节点时检查名称的有效性。 如果名称包含非法字符，则将引发异常。 若要确保名称有效且编码正确，你需要使用**XmlConvert**类进行编码名称，并在应用程序级别对其进行解码。 **XmlWriter**具有执行附加工作以确保生成格式正确的 XML 的方法。  
  
## <a name="see-also"></a>另请参阅  
 [XML 文档对象模型 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
