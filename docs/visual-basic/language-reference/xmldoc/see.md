---
title: '&lt;请参阅&gt;(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: 78311651593d3d4a47c723f64a9a74d4660f7c90
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44248873"
---
# <a name="ltseegt-visual-basic"></a><span data-ttu-id="d022d-102">&lt;请参阅&gt;(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d022d-102">&lt;see&gt; (Visual Basic)</span></span>
<span data-ttu-id="d022d-103">指定指向另一个成员的链接。</span><span class="sxs-lookup"><span data-stu-id="d022d-103">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d022d-104">语法</span><span class="sxs-lookup"><span data-stu-id="d022d-104">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d022d-105">参数</span><span class="sxs-lookup"><span data-stu-id="d022d-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="d022d-106">对可从当前编译环境调用的成员或字段的引用。</span><span class="sxs-lookup"><span data-stu-id="d022d-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="d022d-107">编译器检查是否存在给定的代码元素，并将传递`member`为输出 XML 中的元素名称。</span><span class="sxs-lookup"><span data-stu-id="d022d-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="d022d-108">`member` 必须出现在双引号 (" ") 内。</span><span class="sxs-lookup"><span data-stu-id="d022d-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d022d-109">备注</span><span class="sxs-lookup"><span data-stu-id="d022d-109">Remarks</span></span>  
 <span data-ttu-id="d022d-110">使用`<see>`标记来指定从文本中的链接。</span><span class="sxs-lookup"><span data-stu-id="d022d-110">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="d022d-111">使用[ \<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md)以指示你可能想要的"另请参见"部分中显示的文本。</span><span class="sxs-lookup"><span data-stu-id="d022d-111">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="d022d-112">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="d022d-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d022d-113">示例</span><span class="sxs-lookup"><span data-stu-id="d022d-113">Example</span></span>  
 <span data-ttu-id="d022d-114">此示例使用`<see>`标记中的`UpdateRecord`备注一节来指代`DoesRecordExist`方法。</span><span class="sxs-lookup"><span data-stu-id="d022d-114">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/see_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d022d-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="d022d-115">See Also</span></span>  
 [<span data-ttu-id="d022d-116">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="d022d-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
