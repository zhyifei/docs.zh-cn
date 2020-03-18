---
title: <remarks> - C# 编程指南
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: e37dac9cb9fed1df6ca027f09f2c95dbbc8ea66d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "76793377"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="5423c-102">\<remarks>（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="5423c-102">\<remarks> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="5423c-103">语法</span><span class="sxs-lookup"><span data-stu-id="5423c-103">Syntax</span></span>

```xml
<remarks>description</remarks>
```

## <a name="parameters"></a><span data-ttu-id="5423c-104">参数</span><span class="sxs-lookup"><span data-stu-id="5423c-104">Parameters</span></span>

- `Description`

  <span data-ttu-id="5423c-105">对成员的说明。</span><span class="sxs-lookup"><span data-stu-id="5423c-105">A description of the member.</span></span>

## <a name="remarks"></a><span data-ttu-id="5423c-106">备注</span><span class="sxs-lookup"><span data-stu-id="5423c-106">Remarks</span></span>

<span data-ttu-id="5423c-107">\<remarks> 标记用于添加有关某个类型的信息，从而补充由 [\<summary>](./summary.md) 指定的信息。</span><span class="sxs-lookup"><span data-stu-id="5423c-107">The \<remarks> tag is used to add information about a type, supplementing the information specified with [\<summary>](./summary.md).</span></span> <span data-ttu-id="5423c-108">此信息显示在对象浏览器窗口中。</span><span class="sxs-lookup"><span data-stu-id="5423c-108">This information is displayed in the Object Browser window.</span></span>

<span data-ttu-id="5423c-109">使用 [-doc](../../language-reference/compiler-options/doc-compiler-option.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="5423c-109">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="5423c-110">示例</span><span class="sxs-lookup"><span data-stu-id="5423c-110">Example</span></span>

[!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]

## <a name="see-also"></a><span data-ttu-id="5423c-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5423c-111">See also</span></span>

- [<span data-ttu-id="5423c-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5423c-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5423c-113">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="5423c-113">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
