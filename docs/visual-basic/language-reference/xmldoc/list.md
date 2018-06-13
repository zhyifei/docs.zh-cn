---
title: '&lt;列表&gt;(Visual Basic)'
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
ms.openlocfilehash: f03924217393e1e909b086b282f1c62ddb471522
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33603608"
---
# <a name="ltlistgt-visual-basic"></a><span data-ttu-id="50908-102">&lt;列表&gt;(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="50908-102">&lt;list&gt; (Visual Basic)</span></span>
<span data-ttu-id="50908-103">定义列表或表。</span><span class="sxs-lookup"><span data-stu-id="50908-103">Defines a list or table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50908-104">语法</span><span class="sxs-lookup"><span data-stu-id="50908-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="50908-105">参数</span><span class="sxs-lookup"><span data-stu-id="50908-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="50908-106">列表的类型。</span><span class="sxs-lookup"><span data-stu-id="50908-106">The type of the list.</span></span> <span data-ttu-id="50908-107">项目符号列表、 编号的列表，或有两个列的表"表"的"number"必须是"项目符号"。</span><span class="sxs-lookup"><span data-stu-id="50908-107">Must be a "bullet" for a bulleted list, "number" for a numbered list, or "table" for a two-column table.</span></span>  
  
 `term`  
 <span data-ttu-id="50908-108">仅当`type`是"table"。</span><span class="sxs-lookup"><span data-stu-id="50908-108">Only used when `type` is "table."</span></span> <span data-ttu-id="50908-109">要定义的项，说明标记中定义。</span><span class="sxs-lookup"><span data-stu-id="50908-109">A term to define, which is defined in the description tag.</span></span>  
  
 `description`  
 <span data-ttu-id="50908-110">时`type`是"项目符号"编号"`description`是在列表中的项时`type`是"table"`description`是定义`term`。</span><span class="sxs-lookup"><span data-stu-id="50908-110">When `type` is "bullet" or "number," `description` is an item in the list When `type` is "table," `description` is the definition of `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50908-111">备注</span><span class="sxs-lookup"><span data-stu-id="50908-111">Remarks</span></span>  
 <span data-ttu-id="50908-112">`<listheader>`块定义表或定义列表的标题。</span><span class="sxs-lookup"><span data-stu-id="50908-112">The `<listheader>` block defines the heading of either a table or definition list.</span></span> <span data-ttu-id="50908-113">当定义一个表，只需提供的条目`term`标题中。</span><span class="sxs-lookup"><span data-stu-id="50908-113">When defining a table, you only have to supply an entry for `term` in the heading.</span></span>  
  
 <span data-ttu-id="50908-114">使用指定列表中的每个项`<item>`块。</span><span class="sxs-lookup"><span data-stu-id="50908-114">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="50908-115">在创建时定义列表，则必须将同时指定`term`和`description`。</span><span class="sxs-lookup"><span data-stu-id="50908-115">When creating a definition list, you must specify both `term` and `description`.</span></span> <span data-ttu-id="50908-116">但是，对于表、 项目符号列表中或编号的列表，只需提供的条目`description`。</span><span class="sxs-lookup"><span data-stu-id="50908-116">However, for a table, bulleted list, or numbered list, you only have to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="50908-117">列表或表可以有任意多个`<item>`阻止根据需要。</span><span class="sxs-lookup"><span data-stu-id="50908-117">A list or table can have as many `<item>` blocks as needed.</span></span>  
  
 <span data-ttu-id="50908-118">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="50908-118">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50908-119">示例</span><span class="sxs-lookup"><span data-stu-id="50908-119">Example</span></span>  
 <span data-ttu-id="50908-120">此示例使用`<list>`标记来定义在备注部分中的项目符号列表。</span><span class="sxs-lookup"><span data-stu-id="50908-120">This example uses the `<list>` tag to define a bulleted list in the remarks section.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#5](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/list_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="50908-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="50908-121">See Also</span></span>  
 [<span data-ttu-id="50908-122">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="50908-122">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
