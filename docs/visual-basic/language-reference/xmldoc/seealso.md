---
title: '&lt;seealso&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: a792bbea108bcdf33d430c47773466ef3dccdb0c
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48776566"
---
# <a name="ltseealsogt-visual-basic"></a><span data-ttu-id="5a52a-102">&lt;seealso&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a52a-102">&lt;seealso&gt; (Visual Basic)</span></span>
<span data-ttu-id="5a52a-103">指定的另请参见部分中显示的链接。</span><span class="sxs-lookup"><span data-stu-id="5a52a-103">Specifies a link that appears in the See Also section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a52a-104">语法</span><span class="sxs-lookup"><span data-stu-id="5a52a-104">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5a52a-105">参数</span><span class="sxs-lookup"><span data-stu-id="5a52a-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="5a52a-106">对可从当前编译环境调用的成员或字段的引用。</span><span class="sxs-lookup"><span data-stu-id="5a52a-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="5a52a-107">编译器检查是否存在给定的代码元素，并将传递`member`为输出 XML 中的元素名称。</span><span class="sxs-lookup"><span data-stu-id="5a52a-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="5a52a-108">`member` 必须出现在双引号 (" ") 内。</span><span class="sxs-lookup"><span data-stu-id="5a52a-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5a52a-109">备注</span><span class="sxs-lookup"><span data-stu-id="5a52a-109">Remarks</span></span>  
 <span data-ttu-id="5a52a-110">使用`<seealso>`标记指定你想要的另请参见部分中显示的文本。</span><span class="sxs-lookup"><span data-stu-id="5a52a-110">Use the `<seealso>` tag to specify the text that you want to appear in a See Also section.</span></span> <span data-ttu-id="5a52a-111">使用 [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) 从文本内指定链接。</span><span class="sxs-lookup"><span data-stu-id="5a52a-111">Use [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="5a52a-112">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="5a52a-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a52a-113">示例</span><span class="sxs-lookup"><span data-stu-id="5a52a-113">Example</span></span>  
 <span data-ttu-id="5a52a-114">此示例使用`<seealso>`标记中的`DoesRecordExist`备注一节来指代`UpdateRecord`方法。</span><span class="sxs-lookup"><span data-stu-id="5a52a-114">This example uses the `<seealso>` tag in the `DoesRecordExist` remarks section to refer to the `UpdateRecord` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/seealso_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5a52a-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a52a-115">See Also</span></span>  
 [<span data-ttu-id="5a52a-116">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="5a52a-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
