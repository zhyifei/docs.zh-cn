---
title: <typeparam> - C# 编程指南
ms.date: 07/20/2015
f1_keywords:
- typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
ms.openlocfilehash: 867ecacf58f95533395ded203a8f17bc92558ccf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "76793367"
---
# <a name="typeparam-c-programming-guide"></a><span data-ttu-id="fb20f-102">\<typeparam>（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="fb20f-102">\<typeparam> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="fb20f-103">语法</span><span class="sxs-lookup"><span data-stu-id="fb20f-103">Syntax</span></span>

```xml
<typeparam name="name">description</typeparam>
```

## <a name="parameters"></a><span data-ttu-id="fb20f-104">参数</span><span class="sxs-lookup"><span data-stu-id="fb20f-104">Parameters</span></span>

- `name`

  <span data-ttu-id="fb20f-105">类型参数的名称。</span><span class="sxs-lookup"><span data-stu-id="fb20f-105">The name of the type parameter.</span></span> <span data-ttu-id="fb20f-106">用双引号 (" ") 将名称引起来。</span><span class="sxs-lookup"><span data-stu-id="fb20f-106">Enclose the name in double quotation marks (" ").</span></span>

- `description`

  <span data-ttu-id="fb20f-107">类型参数的说明。</span><span class="sxs-lookup"><span data-stu-id="fb20f-107">A description for the type parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="fb20f-108">备注</span><span class="sxs-lookup"><span data-stu-id="fb20f-108">Remarks</span></span>

<span data-ttu-id="fb20f-109">在泛型类型或方法声明的注释中，应使用 `<typeparam>` 标记来描述类型参数。</span><span class="sxs-lookup"><span data-stu-id="fb20f-109">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="fb20f-110">为泛型类型或方法的每个类型参数添加标记。</span><span class="sxs-lookup"><span data-stu-id="fb20f-110">Add a tag for each type parameter of the generic type or method.</span></span>

<span data-ttu-id="fb20f-111">有关详细信息，请参阅[泛型](../generics/index.md)。</span><span class="sxs-lookup"><span data-stu-id="fb20f-111">For more information, see [Generics](../generics/index.md).</span></span>

<span data-ttu-id="fb20f-112">`<typeparam>` 标记的文本将显示在 IntelliSense、[对象浏览器窗口](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser)代码注释 Web 报表。</span><span class="sxs-lookup"><span data-stu-id="fb20f-112">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](/visualstudio/ide/viewing-the-structure-of-code#BKMK_ObjectBrowser) code comment web report.</span></span>

<span data-ttu-id="fb20f-113">使用 [-doc](../../language-reference/compiler-options/doc-compiler-option.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="fb20f-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="fb20f-114">示例</span><span class="sxs-lookup"><span data-stu-id="fb20f-114">Example</span></span>

[!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]

## <a name="see-also"></a><span data-ttu-id="fb20f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb20f-115">See also</span></span>

- [<span data-ttu-id="fb20f-116">C# 参考</span><span class="sxs-lookup"><span data-stu-id="fb20f-116">C# reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="fb20f-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="fb20f-117">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="fb20f-118">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="fb20f-118">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
