---
title: <param> - C# 编程指南
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: d16070a82531519dd276b2ea999623017769d716
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789762"
---
# <a name="param-c-programming-guide"></a>\<param>（C# 编程指南）

## <a name="syntax"></a>语法

```xml
<param name="name">description</param>
```

## <a name="parameters"></a>参数

- `name`

  方法参数的名称。 用双引号 (" ") 将名称引起来。

- `description`

  参数的说明。

## <a name="remarks"></a>备注

在方法声明的注释中，应使用 \<param> 标记来描述方法参数之一。 若要记录多个参数，请使用多个 \<param > 标记。

\<param> 标记的文本将显示在 IntelliSense、对象浏览器和代码注释 Web 报表中。

使用 [-doc](../../language-reference/compiler-options/doc-compiler-option.md) 进行编译以便将文档注释处理到文件中。

## <a name="example"></a>示例

[!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]

## <a name="see-also"></a>请参阅

- [C# 编程指南](../index.md)
- [建议的文档注释标记](./recommended-tags-for-documentation-comments.md)
