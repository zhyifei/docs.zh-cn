---
title: <returns> - C# 编程指南
ms.date: 07/20/2015
f1_keywords:
- returns
- <returns>
helpviewer_keywords:
- <returns> C# XML tag
- returns C# XML tag
ms.assetid: bb2d9958-62fc-47c7-9511-6311171f119f
ms.openlocfilehash: 784d9effa589c962b8a2b982fd199f74309fb4dc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "76789714"
---
# <a name="returns-c-programming-guide"></a><span data-ttu-id="bde56-102">\<returns>（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="bde56-102">\<returns> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="bde56-103">语法</span><span class="sxs-lookup"><span data-stu-id="bde56-103">Syntax</span></span>

```xml
<returns>description</returns>
```

## <a name="parameters"></a><span data-ttu-id="bde56-104">参数</span><span class="sxs-lookup"><span data-stu-id="bde56-104">Parameters</span></span>

- `description`

  <span data-ttu-id="bde56-105">返回值的说明。</span><span class="sxs-lookup"><span data-stu-id="bde56-105">A description of the return value.</span></span>

## <a name="remarks"></a><span data-ttu-id="bde56-106">备注</span><span class="sxs-lookup"><span data-stu-id="bde56-106">Remarks</span></span>

<span data-ttu-id="bde56-107">在方法声明的注释中应使用 \<returns> 标记来描述返回值。</span><span class="sxs-lookup"><span data-stu-id="bde56-107">The \<returns> tag should be used in the comment for a method declaration to describe the return value.</span></span>

<span data-ttu-id="bde56-108">使用 [-doc](../../language-reference/compiler-options/doc-compiler-option.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="bde56-108">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="bde56-109">示例</span><span class="sxs-lookup"><span data-stu-id="bde56-109">Example</span></span>

[!code-csharp[csProgGuideDocComments#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#10)]

## <a name="see-also"></a><span data-ttu-id="bde56-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bde56-110">See also</span></span>

- [<span data-ttu-id="bde56-111">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="bde56-111">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="bde56-112">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="bde56-112">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
