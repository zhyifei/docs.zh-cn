---
title: '&lt;c&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 556c00fa761a1bce5e922a304706c78893550901
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33599601"
---
# <a name="ltcgt-visual-basic"></a><span data-ttu-id="f4a4e-102">&lt;c&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f4a4e-102">&lt;c&gt; (Visual Basic)</span></span>
<span data-ttu-id="f4a4e-103">指示说明中的文本是代码。</span><span class="sxs-lookup"><span data-stu-id="f4a4e-103">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4a4e-104">语法</span><span class="sxs-lookup"><span data-stu-id="f4a4e-104">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f4a4e-105">参数</span><span class="sxs-lookup"><span data-stu-id="f4a4e-105">Parameters</span></span>  
  
|<span data-ttu-id="f4a4e-106">参数</span><span class="sxs-lookup"><span data-stu-id="f4a4e-106">Parameter</span></span>|<span data-ttu-id="f4a4e-107">描述</span><span class="sxs-lookup"><span data-stu-id="f4a4e-107">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="f4a4e-108">要指示为代码的文本。</span><span class="sxs-lookup"><span data-stu-id="f4a4e-108">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f4a4e-109">备注</span><span class="sxs-lookup"><span data-stu-id="f4a4e-109">Remarks</span></span>  
 <span data-ttu-id="f4a4e-110">`<c>`标记为你提供了一种方法，以指示说明中的文本应标记为代码。</span><span class="sxs-lookup"><span data-stu-id="f4a4e-110">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="f4a4e-111">使用 [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) 指示作为代码的多行文本。</span><span class="sxs-lookup"><span data-stu-id="f4a4e-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="f4a4e-112">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="f4a4e-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f4a4e-113">示例</span><span class="sxs-lookup"><span data-stu-id="f4a4e-113">Example</span></span>  
 <span data-ttu-id="f4a4e-114">此示例使用`<c>`标记在摘要部分，则指示`Counter`是代码。</span><span class="sxs-lookup"><span data-stu-id="f4a4e-114">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/c_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="f4a4e-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4a4e-115">See Also</span></span>  
 [<span data-ttu-id="f4a4e-116">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="f4a4e-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
