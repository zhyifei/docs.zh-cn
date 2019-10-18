---
title: <list> （Visual Basic）
ms.date: 07/20/2015
helpviewer_keywords:
- listheader XML tag
- <item> XML tag
- <list> XML tag
- <listheader> XML tag
- term XML tag
- list XML tag
- <description> XML tag
- description XML tag
- item XML tag
- <term> XML tag
ms.assetid: ec35fced-d58e-4520-a764-0691256e014b
ms.openlocfilehash: 5d4295d485611e75e8b6c8d8f95e079654f0cfa3
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524746"
---
# <a name="list-visual-basic"></a><span data-ttu-id="5494e-102">\<list > （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="5494e-102">\<list> (Visual Basic)</span></span>
<span data-ttu-id="5494e-103">定义列表或表。</span><span class="sxs-lookup"><span data-stu-id="5494e-103">Defines a list or table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5494e-104">语法</span><span class="sxs-lookup"><span data-stu-id="5494e-104">Syntax</span></span>  
  
```xml  
<list type="type">  
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
  
## <a name="parameters"></a><span data-ttu-id="5494e-105">参数</span><span class="sxs-lookup"><span data-stu-id="5494e-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="5494e-106">列表的类型。</span><span class="sxs-lookup"><span data-stu-id="5494e-106">The type of the list.</span></span> <span data-ttu-id="5494e-107">必须是项目符号列表的 "项目符号"、编号列表的 "数字" 或两列表的 "表"。</span><span class="sxs-lookup"><span data-stu-id="5494e-107">Must be a "bullet" for a bulleted list, "number" for a numbered list, or "table" for a two-column table.</span></span>  
  
 `term`  
 <span data-ttu-id="5494e-108">仅在 `type` 为 "table" 时使用。</span><span class="sxs-lookup"><span data-stu-id="5494e-108">Only used when `type` is "table."</span></span> <span data-ttu-id="5494e-109">要定义的术语，在 description 标记中定义。</span><span class="sxs-lookup"><span data-stu-id="5494e-109">A term to define, which is defined in the description tag.</span></span>  
  
 `description`  
 <span data-ttu-id="5494e-110">当 `type` 为 "项目符号" 或 "数字" 时，当 `type` 为 "table" 时，`description` 是列表中的项，`description` 是 `term` 的定义。</span><span class="sxs-lookup"><span data-stu-id="5494e-110">When `type` is "bullet" or "number," `description` is an item in the list When `type` is "table," `description` is the definition of `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5494e-111">备注</span><span class="sxs-lookup"><span data-stu-id="5494e-111">Remarks</span></span>  
 <span data-ttu-id="5494e-112">@No__t_0 块定义表或定义列表的标题。</span><span class="sxs-lookup"><span data-stu-id="5494e-112">The `<listheader>` block defines the heading of either a table or definition list.</span></span> <span data-ttu-id="5494e-113">定义表时，只需为标题中的 `term` 提供条目。</span><span class="sxs-lookup"><span data-stu-id="5494e-113">When defining a table, you only have to supply an entry for `term` in the heading.</span></span>  
  
 <span data-ttu-id="5494e-114">列表中的每一项都指定了一个 `<item>` 块。</span><span class="sxs-lookup"><span data-stu-id="5494e-114">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="5494e-115">创建定义列表时，必须同时指定 `term` 和 `description`。</span><span class="sxs-lookup"><span data-stu-id="5494e-115">When creating a definition list, you must specify both `term` and `description`.</span></span> <span data-ttu-id="5494e-116">但是，对于表、项目符号列表或编号列表，只需为 `description` 提供条目。</span><span class="sxs-lookup"><span data-stu-id="5494e-116">However, for a table, bulleted list, or numbered list, you only have to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="5494e-117">列表或表可以具有任意数量的 `<item>` 块（根据需要）。</span><span class="sxs-lookup"><span data-stu-id="5494e-117">A list or table can have as many `<item>` blocks as needed.</span></span>  
  
 <span data-ttu-id="5494e-118">使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="5494e-118">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5494e-119">示例</span><span class="sxs-lookup"><span data-stu-id="5494e-119">Example</span></span>  
 <span data-ttu-id="5494e-120">此示例使用 `<list>` 标记在 "备注" 部分中定义项目符号列表。</span><span class="sxs-lookup"><span data-stu-id="5494e-120">This example uses the `<list>` tag to define a bulleted list in the remarks section.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="5494e-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="5494e-121">See also</span></span>

- [<span data-ttu-id="5494e-122">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="5494e-122">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
