---
title: 创建新节点时的 XML 元素和属性名验证
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 008cf14e63b8458feebf26eaf27be516bb79f933
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/08/2018
ms.locfileid: "44216036"
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a><span data-ttu-id="bf709-102">创建新节点时的 XML 元素和属性名验证</span><span class="sxs-lookup"><span data-stu-id="bf709-102">XML Element and Attribute Name Verification when Creating New Nodes</span></span>
<span data-ttu-id="bf709-103">XML 文档对象模型 (DOM) 在创建新元素节点或属性节点时检查名称的有效性。</span><span class="sxs-lookup"><span data-stu-id="bf709-103">The XML Document Object Model (DOM) checks the validity of the names when creating new element nodes or attribute nodes.</span></span> <span data-ttu-id="bf709-104">如果名称包含非法字符，则将引发异常。</span><span class="sxs-lookup"><span data-stu-id="bf709-104">If the names contain illegal characters, an exception is thrown.</span></span> <span data-ttu-id="bf709-105">若要确保名称有效且编码正确，需要使用 XmlConvert 类，在应用一级对名称进行编码和解码。</span><span class="sxs-lookup"><span data-stu-id="bf709-105">To ensure that names are valid and encoded correctly, you need to use the **XmlConvert** class to encode the name and decode it back at an application level.</span></span> <span data-ttu-id="bf709-106">XmlWriter 包含执行附加操作的方法，以确保生成格式标准的 XML。</span><span class="sxs-lookup"><span data-stu-id="bf709-106">The **XmlWriter** has methods that do additional work to ensure well-formed XML is generated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf709-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf709-107">See also</span></span>

- [<span data-ttu-id="bf709-108">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="bf709-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
