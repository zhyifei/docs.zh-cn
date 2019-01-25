---
title: '&lt;代码&gt;(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: 8a4708a7b50b0e221c1ebe7f95d4f8ff80cd1ebe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566302"
---
# <a name="ltcodegt-visual-basic"></a><span data-ttu-id="b0f41-102">&lt;代码&gt;(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b0f41-102">&lt;code&gt; (Visual Basic)</span></span>
<span data-ttu-id="b0f41-103">指示该文本是多行代码。</span><span class="sxs-lookup"><span data-stu-id="b0f41-103">Indicates that the text is multiple lines of code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0f41-104">语法</span><span class="sxs-lookup"><span data-stu-id="b0f41-104">Syntax</span></span>  
  
```xml  
<code>content</code>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b0f41-105">参数</span><span class="sxs-lookup"><span data-stu-id="b0f41-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="b0f41-106">要将标记为代码的文本。</span><span class="sxs-lookup"><span data-stu-id="b0f41-106">The text to mark as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0f41-107">备注</span><span class="sxs-lookup"><span data-stu-id="b0f41-107">Remarks</span></span>  
 <span data-ttu-id="b0f41-108">使用`<code>`标记为代码指示多行。</span><span class="sxs-lookup"><span data-stu-id="b0f41-108">Use the `<code>` tag to indicate multiple lines as code.</span></span> <span data-ttu-id="b0f41-109">使用 [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) 指示应将说明内的文本标记为代码。</span><span class="sxs-lookup"><span data-stu-id="b0f41-109">Use [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) to indicate that text within a description should be marked as code.</span></span>  
  
 <span data-ttu-id="b0f41-110">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="b0f41-110">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0f41-111">示例</span><span class="sxs-lookup"><span data-stu-id="b0f41-111">Example</span></span>  
 <span data-ttu-id="b0f41-112">此示例使用\<代码 > 标记以包含示例代码，使用`ID`字段。</span><span class="sxs-lookup"><span data-stu-id="b0f41-112">This example uses the \<code> tag to include example code for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/code_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="b0f41-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0f41-113">See also</span></span>
- [<span data-ttu-id="b0f41-114">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="b0f41-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
