---
title: "加载 DOM 时的空白和有效空白处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b141a0a-50d8-4ebd-83cd-a84449bb22b2
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 82401a18132801f9aa5368832b96be3cb67a8642
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="white-space-and-significant-white-space-handling-when-loading-the-dom"></a>加载 DOM 时的空白和有效空白处理
加载文档，可以将设置选项以保留空白区域并创建**XmlWhitespace**文档树中的节点。 若要创建空白节点，设置**PreserveWhitespace**属性为 true。 如果该属性设置为**false**，这是默认设置，则不创建空白节点。 总是保留有效空白节点，和**XmlSignificantWhitespace**始终在内存中表示此数据，而不考虑的设置创建节点**PreserveWhitespace**标志。  
  
 如果从读取器加载该文档，然后设置**PreserveWhitespace**标志属性**XmlDocument**类会影响创建**XmlWhitespace**节点仅当**WhitespaceHandling**属性**XmlTextReader**未设置为**WhitespaceHandling.None**。 它是值的**WhitespaceHandling**属性上的读取器将优先于该标志的设置上**XmlDocument**。 有关详细信息**XmlSignificantWhitespace**，请参阅<xref:System.Xml.XmlSignificantWhitespace>。  
  
## <a name="see-also"></a>另请参阅  
 [XML 文档对象模型 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
