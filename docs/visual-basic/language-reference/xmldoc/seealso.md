---
title: <seealso> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: 9f857be6d0bd46233a49c7d2ff0931670baa95a6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965294"
---
# <a name="seealso-visual-basic"></a><span data-ttu-id="f52bf-102">\<seealso > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f52bf-102">\<seealso> (Visual Basic)</span></span>
<span data-ttu-id="f52bf-103">指定的另请参见部分中显示的链接。</span><span class="sxs-lookup"><span data-stu-id="f52bf-103">Specifies a link that appears in the See Also section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f52bf-104">语法</span><span class="sxs-lookup"><span data-stu-id="f52bf-104">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f52bf-105">参数</span><span class="sxs-lookup"><span data-stu-id="f52bf-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="f52bf-106">对可从当前编译环境调用的成员或字段的引用。</span><span class="sxs-lookup"><span data-stu-id="f52bf-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="f52bf-107">编译器检查是否存在给定的码位元素，并将 `member` 传递到输出 XML 中的元素名称。</span><span class="sxs-lookup"><span data-stu-id="f52bf-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="f52bf-108">`member` 必须出现在双引号 (" ") 内。</span><span class="sxs-lookup"><span data-stu-id="f52bf-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f52bf-109">备注</span><span class="sxs-lookup"><span data-stu-id="f52bf-109">Remarks</span></span>  
 <span data-ttu-id="f52bf-110">使用`<seealso>`标记指定你想要的另请参见部分中显示的文本。</span><span class="sxs-lookup"><span data-stu-id="f52bf-110">Use the `<seealso>` tag to specify the text that you want to appear in a See Also section.</span></span> <span data-ttu-id="f52bf-111">使用 [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) 从文本内指定链接。</span><span class="sxs-lookup"><span data-stu-id="f52bf-111">Use [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="f52bf-112">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="f52bf-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f52bf-113">示例</span><span class="sxs-lookup"><span data-stu-id="f52bf-113">Example</span></span>  
 <span data-ttu-id="f52bf-114">此示例使用`<seealso>`标记中的`DoesRecordExist`备注一节来指代`UpdateRecord`方法。</span><span class="sxs-lookup"><span data-stu-id="f52bf-114">This example uses the `<seealso>` tag in the `DoesRecordExist` remarks section to refer to the `UpdateRecord` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="f52bf-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="f52bf-115">See also</span></span>
- [<span data-ttu-id="f52bf-116">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="f52bf-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
