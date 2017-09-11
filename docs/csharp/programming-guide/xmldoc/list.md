---
title: "&lt;列表&gt;（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- list
- <list>
dev_langs:
- CSharp
helpviewer_keywords:
- list C# XML tag
- listheader C# XML tag
- <listheader> C# XML tag
- item C# XML tag
- <item> C# XML tag
- <list> C# XML tag
ms.assetid: c9620b1b-c2e6-43f1-ab88-8ab47308ffec
caps.latest.revision: 11
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b9d3dfa60530734a142295c8a8f2c32c4ecd9a47
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="ltlistgt-c-programming-guide"></a><span data-ttu-id="1c4a3-102">&lt;列表&gt;（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="1c4a3-102">&lt;list&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="1c4a3-103">语法</span><span class="sxs-lookup"><span data-stu-id="1c4a3-103">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="1c4a3-104">参数</span><span class="sxs-lookup"><span data-stu-id="1c4a3-104">Parameters</span></span>  
 `term`  
 <span data-ttu-id="1c4a3-105">要定义的术语，将在 `description` 中进行定义。</span><span class="sxs-lookup"><span data-stu-id="1c4a3-105">A term to define, which will be defined in `description`.</span></span>  
  
 `description`  
 <span data-ttu-id="1c4a3-106">项目符号或编号列表中的项或 `term` 的定义。</span><span class="sxs-lookup"><span data-stu-id="1c4a3-106">Either an item in a bullet or numbered list or the definition of a `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c4a3-107">备注</span><span class="sxs-lookup"><span data-stu-id="1c4a3-107">Remarks</span></span>  
 <span data-ttu-id="1c4a3-108">\<listheader> 块用于定义表或定义列表的标题行。</span><span class="sxs-lookup"><span data-stu-id="1c4a3-108">The \<listheader> block is used to define the heading row of either a table or definition list.</span></span> <span data-ttu-id="1c4a3-109">定义表时，只需提供标题中的术语的项。</span><span class="sxs-lookup"><span data-stu-id="1c4a3-109">When defining a table, you only need to supply an entry for term in the heading.</span></span>  
  
 <span data-ttu-id="1c4a3-110">列表中的每个项均使用 \<item> 块指定。</span><span class="sxs-lookup"><span data-stu-id="1c4a3-110">Each item in the list is specified with an \<item> block.</span></span> <span data-ttu-id="1c4a3-111">创建定义列表时，需要同时指定 `term` 和 `description`。</span><span class="sxs-lookup"><span data-stu-id="1c4a3-111">When creating a definition list, you will need to specify both `term` and `description`.</span></span> <span data-ttu-id="1c4a3-112">但是，对于表、项目符号列表或编号列表，只需提供 `description` 的项。</span><span class="sxs-lookup"><span data-stu-id="1c4a3-112">However, for a table, bulleted list, or numbered list, you only need to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="1c4a3-113">列表或表可根据需要具有多个 \<item> 块。</span><span class="sxs-lookup"><span data-stu-id="1c4a3-113">A list or table can have as many \<item> blocks as needed.</span></span>  
  
 <span data-ttu-id="1c4a3-114">使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="1c4a3-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c4a3-115">示例</span><span class="sxs-lookup"><span data-stu-id="1c4a3-115">Example</span></span>  
 <span data-ttu-id="1c4a3-116">[!code-cs[csProgGuideDocComments#6](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/list_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1c4a3-116">[!code-cs[csProgGuideDocComments#6](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/list_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c4a3-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c4a3-117">See Also</span></span>  
 <span data-ttu-id="1c4a3-118">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1c4a3-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="1c4a3-119">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="1c4a3-119">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

