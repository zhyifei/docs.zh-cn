---
title: '&lt;list&gt; - C# 编程指南'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- list
- <list>
helpviewer_keywords:
- list C# XML tag
- listheader C# XML tag
- <listheader> C# XML tag
- item C# XML tag
- <item> C# XML tag
- <list> C# XML tag
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
ms.openlocfilehash: a636fd35355dfa7320c2ca961ddada233c574dbc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563153"
---
# <a name="ltlistgt-c-programming-guide"></a><span data-ttu-id="a6e0c-102">&lt;列表&gt;（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="a6e0c-102">&lt;list&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="a6e0c-103">语法</span><span class="sxs-lookup"><span data-stu-id="a6e0c-103">Syntax</span></span>  
  
```xml  
<list type="bullet" | "number" | "table">  
    <listheader>  
        <term>term</term>  
        <description>description</description>  
    </listheader>  
    <item>  
        <term>term</term>  
        <description>description</description>  
    </item>  
</list>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a6e0c-104">参数</span><span class="sxs-lookup"><span data-stu-id="a6e0c-104">Parameters</span></span>  
 `term`  
 <span data-ttu-id="a6e0c-105">要定义的术语，将在 `description` 中进行定义。</span><span class="sxs-lookup"><span data-stu-id="a6e0c-105">A term to define, which will be defined in `description`.</span></span>  
  
 `description`  
 <span data-ttu-id="a6e0c-106">项目符号或编号列表中的项或 `term` 的定义。</span><span class="sxs-lookup"><span data-stu-id="a6e0c-106">Either an item in a bullet or numbered list or the definition of a `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6e0c-107">备注</span><span class="sxs-lookup"><span data-stu-id="a6e0c-107">Remarks</span></span>  
 <span data-ttu-id="a6e0c-108">\<listheader> 块用于定义表或定义列表的标题行。</span><span class="sxs-lookup"><span data-stu-id="a6e0c-108">The \<listheader> block is used to define the heading row of either a table or definition list.</span></span> <span data-ttu-id="a6e0c-109">定义表时，只需提供标题中的术语的项。</span><span class="sxs-lookup"><span data-stu-id="a6e0c-109">When defining a table, you only need to supply an entry for term in the heading.</span></span>  
  
 <span data-ttu-id="a6e0c-110">列表中的每个项均使用 \<item> 块指定。</span><span class="sxs-lookup"><span data-stu-id="a6e0c-110">Each item in the list is specified with an \<item> block.</span></span> <span data-ttu-id="a6e0c-111">创建定义列表时，需要同时指定 `term` 和 `description`。</span><span class="sxs-lookup"><span data-stu-id="a6e0c-111">When creating a definition list, you will need to specify both `term` and `description`.</span></span> <span data-ttu-id="a6e0c-112">但是，对于表、项目符号列表或编号列表，只需提供 `description` 的项。</span><span class="sxs-lookup"><span data-stu-id="a6e0c-112">However, for a table, bulleted list, or numbered list, you only need to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="a6e0c-113">列表或表可根据需要具有多个 \<item> 块。</span><span class="sxs-lookup"><span data-stu-id="a6e0c-113">A list or table can have as many \<item> blocks as needed.</span></span>  
  
 <span data-ttu-id="a6e0c-114">使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="a6e0c-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6e0c-115">示例</span><span class="sxs-lookup"><span data-stu-id="a6e0c-115">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#6](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/list_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a6e0c-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6e0c-116">See also</span></span>

- [<span data-ttu-id="a6e0c-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="a6e0c-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="a6e0c-118">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="a6e0c-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
