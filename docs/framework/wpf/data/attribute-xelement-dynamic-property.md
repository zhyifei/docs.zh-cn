---
title: 特性（XElement 动态属性）
ms.date: 10/22/2019
ms.topic: reference
ms.openlocfilehash: 2b645575a5b6876ffbb52a999c4e05a2de037493
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921202"
---
# <a name="attribute-xelement-dynamic-property"></a><span data-ttu-id="675c6-102">特性（XElement 动态属性）</span><span class="sxs-lookup"><span data-stu-id="675c6-102">Attribute (XElement dynamic property)</span></span>

<span data-ttu-id="675c6-103">获取一个索引器，该索引器用于检索与指定扩展名对应的属性实例。</span><span class="sxs-lookup"><span data-stu-id="675c6-103">Gets an indexer used to retrieve the attribute instance that corresponds to the specified expanded name.</span></span>

## <a name="syntax"></a><span data-ttu-id="675c6-104">语法</span><span class="sxs-lookup"><span data-stu-id="675c6-104">Syntax</span></span>

```xaml
elem.Attribute[{namespaceName}attribName]
```

## <a name="property-valuereturn-value"></a><span data-ttu-id="675c6-105">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="675c6-105">Property value/return value</span></span>

<span data-ttu-id="675c6-106">一个类型为 `XAttribute Item(String expandedName)` 的索引器。</span><span class="sxs-lookup"><span data-stu-id="675c6-106">An indexer of the type `XAttribute Item(String expandedName)`.</span></span> <span data-ttu-id="675c6-107">此索引器获取指定属性的扩展名，然后返回相应的 <xref:System.Xml.Linq.XAttribute>，如果没有具有指定名称的属性，则返回 `null`。</span><span class="sxs-lookup"><span data-stu-id="675c6-107">This indexer takes the expanded name of the specified attribute and returns the corresponding <xref:System.Xml.Linq.XAttribute>, or `null` if there is no attribute with the specified name.</span></span>

## <a name="remarks"></a><span data-ttu-id="675c6-108">备注</span><span class="sxs-lookup"><span data-stu-id="675c6-108">Remarks</span></span>

<span data-ttu-id="675c6-109">此属性等效于 <xref:System.Xml.Linq.XElement.Attribute%2A> 类的 <xref:System.Xml.Linq.XElement?displayProperty=fullName> 方法。</span><span class="sxs-lookup"><span data-stu-id="675c6-109">This property is equivalent to the <xref:System.Xml.Linq.XElement.Attribute%2A> method of the <xref:System.Xml.Linq.XElement?displayProperty=fullName> class.</span></span>

## <a name="see-also"></a><span data-ttu-id="675c6-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="675c6-110">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=fullName>
- [<span data-ttu-id="675c6-111">XElement 类动态属性</span><span class="sxs-lookup"><span data-stu-id="675c6-111">XElement Class Dynamic Properties</span></span>](attribute-xelement-dynamic-property.md)
- [<span data-ttu-id="675c6-112">“值”</span><span class="sxs-lookup"><span data-stu-id="675c6-112">Value</span></span>](value-xattribute-dynamic-property.md)
