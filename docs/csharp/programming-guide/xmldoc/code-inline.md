---
title: <c> - C# 编程指南
ms.date: 07/20/2015
f1_keywords:
- c
- <c>
helpviewer_keywords:
- text, marking as code [C#]
- code, marking text as [C#]
- c C# XML tag
- <c> C# XML tag
ms.assetid: aad5b16e-a29e-445e-bd0d-eea0b138d7b2
ms.openlocfilehash: d5b28ee6db52d191f8454592d792ac0a1e1dc73b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793454"
---
# <a name="c-c-programming-guide"></a><span data-ttu-id="b2557-102">\<c>（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="b2557-102">\<c> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="b2557-103">语法</span><span class="sxs-lookup"><span data-stu-id="b2557-103">Syntax</span></span>

```xml
<c>text</c>
```

## <a name="parameters"></a><span data-ttu-id="b2557-104">参数</span><span class="sxs-lookup"><span data-stu-id="b2557-104">Parameters</span></span>

- `text`

  <span data-ttu-id="b2557-105">要指示为代码的文本。</span><span class="sxs-lookup"><span data-stu-id="b2557-105">The text you would like to indicate as code.</span></span>

## <a name="remarks"></a><span data-ttu-id="b2557-106">备注</span><span class="sxs-lookup"><span data-stu-id="b2557-106">Remarks</span></span>

<span data-ttu-id="b2557-107">使用 \<c> 标记可以指示应将说明内的文本标记为代码。</span><span class="sxs-lookup"><span data-stu-id="b2557-107">The \<c> tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="b2557-108">使用 [\<code>](./code.md) 指示作为代码的多行文本。</span><span class="sxs-lookup"><span data-stu-id="b2557-108">Use [\<code>](./code.md) to indicate multiple lines as code.</span></span>

<span data-ttu-id="b2557-109">使用 [-doc](../../language-reference/compiler-options/doc-compiler-option.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="b2557-109">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="b2557-110">示例</span><span class="sxs-lookup"><span data-stu-id="b2557-110">Example</span></span>

[!code-csharp[csProgGuideDocComments#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#2)]
  
## <a name="see-also"></a><span data-ttu-id="b2557-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="b2557-111">See also</span></span>

- [<span data-ttu-id="b2557-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="b2557-112">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="b2557-113">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="b2557-113">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
