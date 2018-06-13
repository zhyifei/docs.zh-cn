---
title: '&lt;备注&gt;(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: 6e4e280760b9238fdc403ac5fe586743334e4c69
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33598178"
---
# <a name="ltremarksgt-visual-basic"></a><span data-ttu-id="10052-102">&lt;备注&gt;(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="10052-102">&lt;remarks&gt; (Visual Basic)</span></span>
<span data-ttu-id="10052-103">指定成员的备注部分。</span><span class="sxs-lookup"><span data-stu-id="10052-103">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10052-104">语法</span><span class="sxs-lookup"><span data-stu-id="10052-104">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="10052-105">参数</span><span class="sxs-lookup"><span data-stu-id="10052-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="10052-106">对成员的说明。</span><span class="sxs-lookup"><span data-stu-id="10052-106">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10052-107">备注</span><span class="sxs-lookup"><span data-stu-id="10052-107">Remarks</span></span>  
 <span data-ttu-id="10052-108">使用`<remarks>`标记来将有关补充与指定的信息的类型信息添加[\<摘要 >](../../../visual-basic/language-reference/xmldoc/summary.md)。</span><span class="sxs-lookup"><span data-stu-id="10052-108">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md).</span></span>  
  
 <span data-ttu-id="10052-109">此信息显示在对象浏览器。</span><span class="sxs-lookup"><span data-stu-id="10052-109">This information appears in the Object Browser.</span></span> <span data-ttu-id="10052-110">有关对象浏览器的信息，请参阅[查看代码结构](/visualstudio/ide/viewing-the-structure-of-code)。</span><span class="sxs-lookup"><span data-stu-id="10052-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="10052-111">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="10052-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="10052-112">示例</span><span class="sxs-lookup"><span data-stu-id="10052-112">Example</span></span>  
 <span data-ttu-id="10052-113">此示例使用`<remarks>`标记解释`UpdateRecord`方法执行。</span><span class="sxs-lookup"><span data-stu-id="10052-113">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/remarks_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="10052-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="10052-114">See Also</span></span>  
 [<span data-ttu-id="10052-115">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="10052-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
