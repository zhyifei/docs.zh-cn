---
title: <typeparamref> - C# 编程指南
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: 266eadad322fd3c4167c7a911cb57ef1e1333012
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "76789661"
---
# <a name="typeparamref-c-programming-guide"></a><span data-ttu-id="e209e-102">\<typeparamref>（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="e209e-102">\<typeparamref> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="e209e-103">语法</span><span class="sxs-lookup"><span data-stu-id="e209e-103">Syntax</span></span>

```xml
<typeparamref name="name"/>
```

## <a name="parameters"></a><span data-ttu-id="e209e-104">参数</span><span class="sxs-lookup"><span data-stu-id="e209e-104">Parameters</span></span>

- `name`

  <span data-ttu-id="e209e-105">类型参数的名称。</span><span class="sxs-lookup"><span data-stu-id="e209e-105">The name of the type parameter.</span></span> <span data-ttu-id="e209e-106">用双引号 (" ") 将名称引起来。</span><span class="sxs-lookup"><span data-stu-id="e209e-106">Enclose the name in double quotation marks (" ").</span></span>

## <a name="remarks"></a><span data-ttu-id="e209e-107">备注</span><span class="sxs-lookup"><span data-stu-id="e209e-107">Remarks</span></span>

<span data-ttu-id="e209e-108">有关泛型类型中的类型参数及方法的详细信息，请参阅[泛型](../generics/index.md)。</span><span class="sxs-lookup"><span data-stu-id="e209e-108">For more information on type parameters in generic types and methods, see [Generics](../generics/index.md).</span></span>

<span data-ttu-id="e209e-109">通过此标记，文档文件的使用者可显著设置字体格式，例如采用斜体。</span><span class="sxs-lookup"><span data-stu-id="e209e-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>

<span data-ttu-id="e209e-110">使用 [-doc](../../language-reference/compiler-options/doc-compiler-option.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="e209e-110">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="e209e-111">示例</span><span class="sxs-lookup"><span data-stu-id="e209e-111">Example</span></span>

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a><span data-ttu-id="e209e-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e209e-112">See also</span></span>

- [<span data-ttu-id="e209e-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="e209e-113">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="e209e-114">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="e209e-114">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
