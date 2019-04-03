---
title: <list> (Visual Basic)
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
ms.openlocfilehash: 7d7b85867f4c701322c5e6c31f2d89ab38fad05d
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58818523"
---
# <a name="list-visual-basic"></a><span data-ttu-id="94e89-102">\<列表 > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="94e89-102">\<list> (Visual Basic)</span></span>
<span data-ttu-id="94e89-103">定义列表或表。</span><span class="sxs-lookup"><span data-stu-id="94e89-103">Defines a list or table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94e89-104">语法</span><span class="sxs-lookup"><span data-stu-id="94e89-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="94e89-105">参数</span><span class="sxs-lookup"><span data-stu-id="94e89-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="94e89-106">列表的类型。</span><span class="sxs-lookup"><span data-stu-id="94e89-106">The type of the list.</span></span> <span data-ttu-id="94e89-107">对于项目符号列表、 编号的列表，或两列的表"表"的"number"必须为"bullet"。</span><span class="sxs-lookup"><span data-stu-id="94e89-107">Must be a "bullet" for a bulleted list, "number" for a numbered list, or "table" for a two-column table.</span></span>  
  
 `term`  
 <span data-ttu-id="94e89-108">仅当使用`type`是"table"。</span><span class="sxs-lookup"><span data-stu-id="94e89-108">Only used when `type` is "table."</span></span> <span data-ttu-id="94e89-109">要定义的术语，说明标记中定义。</span><span class="sxs-lookup"><span data-stu-id="94e89-109">A term to define, which is defined in the description tag.</span></span>  
  
 `description`  
 <span data-ttu-id="94e89-110">当`type`"bullet"或"数字"`description`是列表中的项时`type`是"table"`description`的定义是`term`。</span><span class="sxs-lookup"><span data-stu-id="94e89-110">When `type` is "bullet" or "number," `description` is an item in the list When `type` is "table," `description` is the definition of `term`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94e89-111">备注</span><span class="sxs-lookup"><span data-stu-id="94e89-111">Remarks</span></span>  
 <span data-ttu-id="94e89-112">`<listheader>`块定义的表或定义列表的标题。</span><span class="sxs-lookup"><span data-stu-id="94e89-112">The `<listheader>` block defines the heading of either a table or definition list.</span></span> <span data-ttu-id="94e89-113">在定义表时，只需提供的条目`term`标题中。</span><span class="sxs-lookup"><span data-stu-id="94e89-113">When defining a table, you only have to supply an entry for `term` in the heading.</span></span>  
  
 <span data-ttu-id="94e89-114">使用指定列表中的每个项`<item>`块。</span><span class="sxs-lookup"><span data-stu-id="94e89-114">Each item in the list is specified with an `<item>` block.</span></span> <span data-ttu-id="94e89-115">创建定义列表时，必须指定`term`和`description`。</span><span class="sxs-lookup"><span data-stu-id="94e89-115">When creating a definition list, you must specify both `term` and `description`.</span></span> <span data-ttu-id="94e89-116">但是，对于表、 项目符号列表或编号的列表，只需提供的条目`description`。</span><span class="sxs-lookup"><span data-stu-id="94e89-116">However, for a table, bulleted list, or numbered list, you only have to supply an entry for `description`.</span></span>  
  
 <span data-ttu-id="94e89-117">列表或表可以有任意多个`<item>`根据需要将阻止。</span><span class="sxs-lookup"><span data-stu-id="94e89-117">A list or table can have as many `<item>` blocks as needed.</span></span>  
  
 <span data-ttu-id="94e89-118">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="94e89-118">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="94e89-119">示例</span><span class="sxs-lookup"><span data-stu-id="94e89-119">Example</span></span>  
 <span data-ttu-id="94e89-120">此示例使用`<list>`标记以在备注部分中定义的项目符号列表。</span><span class="sxs-lookup"><span data-stu-id="94e89-120">This example uses the `<list>` tag to define a bulleted list in the remarks section.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="94e89-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="94e89-121">See also</span></span>

- [<span data-ttu-id="94e89-122">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="94e89-122">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
