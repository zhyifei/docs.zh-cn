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
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a><span data-ttu-id="5f638-102">创建新节点时的 XML 元素和属性名验证</span><span class="sxs-lookup"><span data-stu-id="5f638-102">XML Element and Attribute Name Verification when Creating New Nodes</span></span>
<span data-ttu-id="5f638-103">XML 文档对象模型 (DOM) 在创建新元素节点或属性节点时检查名称的有效性。</span><span class="sxs-lookup"><span data-stu-id="5f638-103">The XML Document Object Model (DOM) checks the validity of the names when creating new element nodes or attribute nodes.</span></span> <span data-ttu-id="5f638-104">如果名称包含非法字符，则将引发异常。</span><span class="sxs-lookup"><span data-stu-id="5f638-104">If the names contain illegal characters, an exception is thrown.</span></span> <span data-ttu-id="5f638-105">若要确保名称有效且编码正确，需要使用 XmlConvert 类，在应用一级对名称进行编码和解码。</span><span class="sxs-lookup"><span data-stu-id="5f638-105">To ensure that names are valid and encoded correctly, you need to use the **XmlConvert** class to encode the name and decode it back at an application level.</span></span> <span data-ttu-id="5f638-106">XmlWriter 包含执行附加操作的方法，以确保生成格式标准的 XML。</span><span class="sxs-lookup"><span data-stu-id="5f638-106">The **XmlWriter** has methods that do additional work to ensure well-formed XML is generated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f638-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f638-107">See Also</span></span>  
 [<span data-ttu-id="5f638-108">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="5f638-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
