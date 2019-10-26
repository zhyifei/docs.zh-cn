---
title: Xml（XElement 动态属性）
ms.date: 10/22/2019
ms.topic: reference
apiname:
- XElement.Xml
ms.openlocfilehash: 9bac9797f397a0bea1dda36bf864f88293061893
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921034"
---
# <a name="xml-xelement-dynamic-property"></a>Xml（XElement 动态属性）

获取元素的非格式化 XML 内容。

## <a name="syntax"></a>语法

```xaml
elem.Xml
```

## <a name="property-valuereturn-value"></a>属性值/返回值

表示元素的非格式化 XML 内容的 <xref:System.String>。

## <a name="remarks"></a>备注

此属性等效于 <xref:System.Xml.Linq.XNode.ToString(System.Xml.Linq.SaveOptions)> 类的 <xref:System.Xml.Linq.XNode?displayProperty=fullName> 方法，其 `SaveOptions` 参数设置为 <xref:System.Xml.Linq.SaveOptions>。

## <a name="see-also"></a>请参阅

- [XElement 类动态属性](attribute-xelement-dynamic-property.md)
- [“值”](value-xelement-dynamic-property.md)
