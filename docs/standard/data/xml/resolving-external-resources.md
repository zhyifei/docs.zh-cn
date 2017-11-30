---
title: "解析外部资源"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad3fa320-4b8f-4e5c-b549-01157591007a
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 824a35ee5d4ecafc45167ff3f4bc89802af4ed96
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="resolving-external-resources"></a>解析外部资源
**XmlResolver**属性**XmlDocument**由**XmlDocument**类用来定位没有内联 XML 数据，如外部文档类型的资源定义 (Dtd)、 实体和架构。 这些项可以位于网络或本地驱动器上，并通过统一资源标识符 (URI) 进行标识。 这允许**XmlDocument**若要解决**EntityReference** ，会在文档中存在验证根据外部 DTD 或架构文档的节点。  
  
## <a name="fully-trusted-xmldocument"></a>完全受信任的 XmlDocument  
 **XmlResolver**属性会影响的功能**XmlDocument.Load**方法。 下的表显示如何**XmlDocument.XmlResolver**时起作用属性**XmlDocument**对象是完全受信任。 下表显示**XmlDocument.Load**方法负载的输入时**TextReader**，**字符串**，**流**，或**URI**。 此表不适用于**负载**方法如果**XmlDocument**从加载**XmlReader**。  
  
|XmlResolver 属性|函数|说明|  
|--------------------------|--------------|-----------|  
|属性设置为**XmlResolver**以前已创建并具有已由用户对其进行设置的属性的类。|**XmlDocument**使用**XmlResolver**给定来解析文件名称，以解析对外部资源，如 Dtd、 实体和架构引用。<br /><br /> **XmlResolver**还在解析外部添加或编辑中的节点时所需的资源时使用**XmlDocument**。|**XmlResolver**赋予**XmlDocument**是需要定位和解析外部资源时，需要使用冲突解决程序。|  
|属性设置为**null** (**执行任何操作**在 Microsoft Visual Basic.NET)。|不支持需要外部资源的功能，如定位外部架构或 DTD。 也不能解析外部实体，而且也不支持执行编辑功能（如插入需要解析的实体节点）。|**XmlDocument**匿名加载文件，而且不会尝试解析任何其他资源。|  
|不设置此属性，而是将其保留为默认状态。|**XmlUrlResolver**替换为 NULL 实例化并通过使用凭据**XmlDocument**时解析文件名称和定位外部 Dtd、 实体和架构，和**null**编辑节点时使用的凭据。||  
  
 下表显示**XmlDocument.Load**方法时的输入**负载**是**XmlReader**和**XmlDocument**是完全受信任。  
  
|XmlResolver 属性|函数|说明|  
|--------------------------|--------------|-----------|  
|**XmlResolver**使用类**XmlDocument**是正在使用的相同类**XmlReader**。|**XmlDocument**使用**XmlResolver** ，已分配给**XmlReader**。<br /><br /> **XmlDocument.Resolver**属性不能为设置，而不考虑**XmlDocument**信任级别，因为它获取**XmlResolver**从**XmlReader**。 不能尝试替代的设置**XmlReaders** **XmlResolver**通过设置**XmlResolver**属性**XmlDocument**.|**XmlReader**可以是**XmlTextReader**， **XmlValidatingReader**，或自己编写的读取器。 如果使用的读取器支持实体解析，则解析外部实体。 如果传递的读取器不支持实体引用，那么就不解析实体引用。|  
  
## <a name="semi-trusted-xmldocument"></a>不完全受信任的 XmlDocument  
 下表显示如何**XmlDocument.XmlResolver**属性在该对象不完全受信任时才有效。 此表适用于**XmlDocument.Load**方法负载的输入时**TextReader**，**字符串**，**流**，或**URI**。 此表不适用于**负载**方法如果**XmlDocument**从加载**XmlReader**。  
  
|XmlResolver 属性|函数|说明|  
|--------------------------|--------------|-----------|  
|在不完全受信任的方案中， **XmlResolver**属性不能设置为除 null 之外的任何内容。|**XmlUrlResolver**与**null**将实例化并使用凭据**XmlDocument**时解析文件名称和定位外部 Dtd、 实体和架构，和**null**编辑节点时使用的凭据。|此行为是相同的行为时**XmlResolver**属性不是设置，但保留其默认状态。<br /><br /> **XmlDocument**对所有操作使用匿名权限。|  
|属性设置为**null** (**执行任何操作**在 Microsoft Visual Basic.NET)。|不支持需要外部资源的功能，如定位外部架构或 DTD。 也不能解析外部实体，而且也不支持执行编辑功能（如插入需要解析的实体节点）。|当该属性是**null**，行为是相同的不管**XmlDocument**是完全受信任或不完全受信任。|  
|不设置此属性，而是将其保留为默认状态。|**XmlUrlResolver**与**null**将实例化并使用凭据**XmlDocument**时解析文件名称和定位外部 Dtd、 实体和架构，和**null**编辑节点时使用的凭据。|**XmlDocument**对所有操作使用匿名权限。|  
  
 此表适用于**XmlDocument.Load**方法时的输入**负载**是**XmlReader**，和**XmlDocument**是不完全受信任。  
  
|XmlResolver 属性|函数|说明|  
|--------------------------|--------------|-----------|  
|**XmlResolver**使用类**XmlDocument**为正在使用的同一**XmlReader**。|**XmlDocument**使用**XmlResolver** ，已分配给**XmlReader**。<br /><br /> **XmlDocument.Resolver**属性不能为设置，而不考虑**XmlDocument**信任级别，因为它获取**XmlResolver**从**XmlReader**。 不能尝试替代的设置**XmlReaders** **XmlResolver**通过设置**XmlResolver**属性**XmlDocument**.|**XmlReader**可以是**XmlTextReader**、 验证<xref:System.Xml.XmlReader>，或自己编写的读取器。 如果使用的读取器支持实体解析，则解析外部实体。 如果传递的读取器不支持实体引用，那么就不解析实体引用。|  
  
 将 XmlResolver 设置为包含正确的凭据后，将可以访问外部资源。  
  
> [!NOTE]
>  没有方法来检索**XmlResolver**属性。 这有助于防止用户重用**XmlResolver**了凭据已设置。 此外，如果**XmlTextReader**或验证<xref:System.Xml.XmlReader>用于加载**XmlDocument**和**XmlDocument**具有已设置，从解析程序解析程序不会缓存这些读取器**XmlDocument**后**负载**阶段，因为这也会带来安全风险。  
  
 有关详细信息，请参阅 <xref:System.Xml.XmlResolver> 引用页的“备注”部分。  
  
## <a name="see-also"></a>另请参阅  
 [XML 文档对象模型 (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
