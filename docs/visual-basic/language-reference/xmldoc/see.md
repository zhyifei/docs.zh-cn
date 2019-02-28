---
title: <see> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: c0f1293fa0161a9a11b4e80301f5c4c4ddffe7b1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969292"
---
# <a name="see-visual-basic"></a><span data-ttu-id="b8fca-102">\<请参阅 > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8fca-102">\<see> (Visual Basic)</span></span>
<span data-ttu-id="b8fca-103">指定指向另一个成员的链接。</span><span class="sxs-lookup"><span data-stu-id="b8fca-103">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8fca-104">语法</span><span class="sxs-lookup"><span data-stu-id="b8fca-104">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b8fca-105">参数</span><span class="sxs-lookup"><span data-stu-id="b8fca-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="b8fca-106">对可从当前编译环境调用的成员或字段的引用。</span><span class="sxs-lookup"><span data-stu-id="b8fca-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="b8fca-107">编译器检查是否存在给定的码位元素，并将 `member` 传递到输出 XML 中的元素名称。</span><span class="sxs-lookup"><span data-stu-id="b8fca-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="b8fca-108">`member` 必须出现在双引号 (" ") 内。</span><span class="sxs-lookup"><span data-stu-id="b8fca-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8fca-109">备注</span><span class="sxs-lookup"><span data-stu-id="b8fca-109">Remarks</span></span>  
 <span data-ttu-id="b8fca-110">使用`<see>`标记来指定从文本中的链接。</span><span class="sxs-lookup"><span data-stu-id="b8fca-110">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="b8fca-111">使用[ \<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md)以指示你可能想要的"另请参见"部分中显示的文本。</span><span class="sxs-lookup"><span data-stu-id="b8fca-111">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="b8fca-112">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="b8fca-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8fca-113">示例</span><span class="sxs-lookup"><span data-stu-id="b8fca-113">Example</span></span>  
 <span data-ttu-id="b8fca-114">此示例使用`<see>`标记中的`UpdateRecord`备注一节来指代`DoesRecordExist`方法。</span><span class="sxs-lookup"><span data-stu-id="b8fca-114">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="b8fca-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="b8fca-115">See also</span></span>
- [<span data-ttu-id="b8fca-116">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="b8fca-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
