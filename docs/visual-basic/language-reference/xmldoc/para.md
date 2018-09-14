---
title: '&lt;para&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: fa11c713a5ed5793b50865753f8bcdeaabf56e83
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45515010"
---
# <a name="ltparagt-visual-basic"></a><span data-ttu-id="15b71-102">&lt;para&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="15b71-102">&lt;para&gt; (Visual Basic)</span></span>
<span data-ttu-id="15b71-103">指定内容的格式设置为一个段落。</span><span class="sxs-lookup"><span data-stu-id="15b71-103">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15b71-104">语法</span><span class="sxs-lookup"><span data-stu-id="15b71-104">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="15b71-105">参数</span><span class="sxs-lookup"><span data-stu-id="15b71-105">Parameters</span></span>  
 `content`  
 <span data-ttu-id="15b71-106">段落文本。</span><span class="sxs-lookup"><span data-stu-id="15b71-106">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="15b71-107">备注</span><span class="sxs-lookup"><span data-stu-id="15b71-107">Remarks</span></span>  
 <span data-ttu-id="15b71-108">`<para>`标记是用于标记内，例如[\<摘要 >](../../../visual-basic/language-reference/xmldoc/summary.md)， [\<备注 >](../../../visual-basic/language-reference/xmldoc/remarks.md)，或[\<返回 >](../../../visual-basic/language-reference/xmldoc/returns.md)，并允许您向文本添加结构。</span><span class="sxs-lookup"><span data-stu-id="15b71-108">The `<para>` tag is for use inside a tag, such as [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md), [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md), or [\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="15b71-109">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="15b71-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="15b71-110">示例</span><span class="sxs-lookup"><span data-stu-id="15b71-110">Example</span></span>  
 <span data-ttu-id="15b71-111">此示例使用`<para>`拆分备注部分的标记`UpdateRecord`分成两个段落的方法。</span><span class="sxs-lookup"><span data-stu-id="15b71-111">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/para_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="15b71-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="15b71-112">See Also</span></span>  
 [<span data-ttu-id="15b71-113">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="15b71-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
