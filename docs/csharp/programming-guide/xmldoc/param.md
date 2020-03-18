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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "76789762"
---
# <a name="param-c-programming-guide"></a><span data-ttu-id="50104-102">\<param>（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="50104-102">\<param> (C# programming guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="50104-103">语法</span><span class="sxs-lookup"><span data-stu-id="50104-103">Syntax</span></span>

```xml
<param name="name">description</param>
```

## <a name="parameters"></a><span data-ttu-id="50104-104">参数</span><span class="sxs-lookup"><span data-stu-id="50104-104">Parameters</span></span>

- `name`

  <span data-ttu-id="50104-105">方法参数的名称。</span><span class="sxs-lookup"><span data-stu-id="50104-105">The name of a method parameter.</span></span> <span data-ttu-id="50104-106">用双引号 (" ") 将名称引起来。</span><span class="sxs-lookup"><span data-stu-id="50104-106">Enclose the name in double quotation marks (" ").</span></span>

- `description`

  <span data-ttu-id="50104-107">参数的说明。</span><span class="sxs-lookup"><span data-stu-id="50104-107">A description for the parameter.</span></span>

## <a name="remarks"></a><span data-ttu-id="50104-108">备注</span><span class="sxs-lookup"><span data-stu-id="50104-108">Remarks</span></span>

<span data-ttu-id="50104-109">在方法声明的注释中，应使用 \<param> 标记来描述方法参数之一。</span><span class="sxs-lookup"><span data-stu-id="50104-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="50104-110">若要记录多个参数，请使用多个 \<param > 标记。</span><span class="sxs-lookup"><span data-stu-id="50104-110">To document multiple parameters, use multiple \<param> tags.</span></span>

<span data-ttu-id="50104-111">\<param> 标记的文本将显示在 IntelliSense、对象浏览器和代码注释 Web 报表中。</span><span class="sxs-lookup"><span data-stu-id="50104-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>

<span data-ttu-id="50104-112">使用 [-doc](../../language-reference/compiler-options/doc-compiler-option.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="50104-112">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>

## <a name="example"></a><span data-ttu-id="50104-113">示例</span><span class="sxs-lookup"><span data-stu-id="50104-113">Example</span></span>

[!code-csharp[csProgGuideDocComments#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#1)]

## <a name="see-also"></a><span data-ttu-id="50104-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="50104-114">See also</span></span>

- [<span data-ttu-id="50104-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="50104-115">C# programming guide</span></span>](../index.md)
- [<span data-ttu-id="50104-116">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="50104-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
