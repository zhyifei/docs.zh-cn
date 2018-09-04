---
title: '&lt;c&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 06c6899895f278fdf652725a05ecc7229805f4d4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43563867"
---
# <a name="ltcgt-visual-basic"></a><span data-ttu-id="fdf62-102">&lt;c&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fdf62-102">&lt;c&gt; (Visual Basic)</span></span>
<span data-ttu-id="fdf62-103">指示说明中的文本是代码。</span><span class="sxs-lookup"><span data-stu-id="fdf62-103">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdf62-104">语法</span><span class="sxs-lookup"><span data-stu-id="fdf62-104">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fdf62-105">参数</span><span class="sxs-lookup"><span data-stu-id="fdf62-105">Parameters</span></span>  
  
|<span data-ttu-id="fdf62-106">参数</span><span class="sxs-lookup"><span data-stu-id="fdf62-106">Parameter</span></span>|<span data-ttu-id="fdf62-107">描述</span><span class="sxs-lookup"><span data-stu-id="fdf62-107">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="fdf62-108">要指示为代码的文本。</span><span class="sxs-lookup"><span data-stu-id="fdf62-108">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fdf62-109">备注</span><span class="sxs-lookup"><span data-stu-id="fdf62-109">Remarks</span></span>  
 <span data-ttu-id="fdf62-110">`<c>`标记为您提供了一种方法，以指示说明中的文本应标记为代码。</span><span class="sxs-lookup"><span data-stu-id="fdf62-110">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="fdf62-111">使用 [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) 指示作为代码的多行文本。</span><span class="sxs-lookup"><span data-stu-id="fdf62-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="fdf62-112">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="fdf62-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdf62-113">示例</span><span class="sxs-lookup"><span data-stu-id="fdf62-113">Example</span></span>  
 <span data-ttu-id="fdf62-114">此示例使用`<c>`指示的摘要部分中的标记`Counter`是代码。</span><span class="sxs-lookup"><span data-stu-id="fdf62-114">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/c_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="fdf62-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="fdf62-115">See Also</span></span>  
 [<span data-ttu-id="fdf62-116">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="fdf62-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
