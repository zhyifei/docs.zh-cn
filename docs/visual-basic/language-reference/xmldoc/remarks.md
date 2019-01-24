---
title: '&lt;备注&gt;(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: 137e2fcd36d5d7618e0193461ebf7ca70b24d19f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737645"
---
# <a name="ltremarksgt-visual-basic"></a><span data-ttu-id="48ec5-102">&lt;备注&gt;(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="48ec5-102">&lt;remarks&gt; (Visual Basic)</span></span>
<span data-ttu-id="48ec5-103">指定成员的备注部分。</span><span class="sxs-lookup"><span data-stu-id="48ec5-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48ec5-104">语法</span><span class="sxs-lookup"><span data-stu-id="48ec5-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="48ec5-105">参数</span><span class="sxs-lookup"><span data-stu-id="48ec5-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="48ec5-106">对成员的说明。</span><span class="sxs-lookup"><span data-stu-id="48ec5-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48ec5-107">备注</span><span class="sxs-lookup"><span data-stu-id="48ec5-107">Remarks</span></span>  
 <span data-ttu-id="48ec5-108">使用`<remarks>`标记添加有关某个类型，对与指定的信息进行了补充[\<摘要 >](../../../visual-basic/language-reference/xmldoc/summary.md)。</span><span class="sxs-lookup"><span data-stu-id="48ec5-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="48ec5-109">此信息显示在对象浏览器中。</span><span class="sxs-lookup"><span data-stu-id="48ec5-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="48ec5-110">对象浏览器有关的信息，请参阅[查看代码结构](/visualstudio/ide/viewing-the-structure-of-code)。</span><span class="sxs-lookup"><span data-stu-id="48ec5-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="48ec5-111">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="48ec5-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48ec5-112">示例</span><span class="sxs-lookup"><span data-stu-id="48ec5-112">Example</span></span>  
 <span data-ttu-id="48ec5-113">此示例使用`<remarks>`标记解释`UpdateRecord`方法执行。</span><span class="sxs-lookup"><span data-stu-id="48ec5-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="48ec5-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="48ec5-114">See also</span></span>
- [<span data-ttu-id="48ec5-115">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="48ec5-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
