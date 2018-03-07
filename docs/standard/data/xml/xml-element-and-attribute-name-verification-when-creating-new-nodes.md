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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 36b9761cefb1dba47c88d053773c89e4312dee9d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a>创建新节点时的 XML 元素和属性名验证
XML 文档对象模型 (DOM) 在创建新元素节点或属性节点时检查名称的有效性。 如果名称包含非法字符，则将引发异常。 若要确保名称有效且编码正确，需要使用 XmlConvert 类，在应用一级对名称进行编码和解码。 XmlWriter 包含执行附加操作的方法，以确保生成格式标准的 XML。  
  
## <a name="see-also"></a>请参阅  
 [XML 文档对象模型 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
