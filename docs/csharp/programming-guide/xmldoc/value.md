---
title: <value> - C# 编程指南
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: 120805346672738e614743ab8c98388b8dbac0f7
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793350"
---
# <a name="value-c-programming-guide"></a><span data-ttu-id="1d49c-102">\<value>（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="1d49c-102">\<value> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="1d49c-103">语法</span><span class="sxs-lookup"><span data-stu-id="1d49c-103">Syntax</span></span>

```xml
<value>property-description</value>
```

## <a name="parameters"></a><span data-ttu-id="1d49c-104">参数</span><span class="sxs-lookup"><span data-stu-id="1d49c-104">Parameters</span></span>

- `property-description`

  <span data-ttu-id="1d49c-105">属性的说明。</span><span class="sxs-lookup"><span data-stu-id="1d49c-105">A description for the property.</span></span>

## <a name="remarks"></a><span data-ttu-id="1d49c-106">备注</span><span class="sxs-lookup"><span data-stu-id="1d49c-106">Remarks</span></span>

<span data-ttu-id="1d49c-107">\<value> 标记可以描述属性表示的值。</span><span class="sxs-lookup"><span data-stu-id="1d49c-107">The \<value> tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="1d49c-108">请注意，在 Visual Studio .NET 开发环境中通过代码向导添加属性时，将添加新属性的 [\<summary>](./summary.md) 标记。</span><span class="sxs-lookup"><span data-stu-id="1d49c-108">Note that when you add a property via code wizard in the Visual Studio .NET development environment, it will add a [\<summary>](./summary.md) tag for the new property.</span></span> <span data-ttu-id="1d49c-109">然后，应手动添加 \<value> 标记，描述属性表示的值。</span><span class="sxs-lookup"><span data-stu-id="1d49c-109">You should then manually add a \<value> tag to describe the value that the property represents.</span></span>

<span data-ttu-id="1d49c-110">使用 [-doc](../../language-reference/compiler-options/doc-compiler-option.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="1d49c-110">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="1d49c-111">示例</span><span class="sxs-lookup"><span data-stu-id="1d49c-111">Example</span></span>

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]

## <a name="see-also"></a><span data-ttu-id="1d49c-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="1d49c-112">See also</span></span>

- [<span data-ttu-id="1d49c-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="1d49c-113">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="1d49c-114">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="1d49c-114">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
