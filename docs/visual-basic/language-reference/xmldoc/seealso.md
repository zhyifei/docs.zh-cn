---
title: '&lt;另请参阅&gt;(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: 1d45c0c5fa95de9cfa345c0bdbf496aa227b9af5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604674"
---
# <a name="ltseealsogt-visual-basic"></a><span data-ttu-id="ab5d1-102">&lt;另请参阅&gt;(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ab5d1-102">&lt;seealso&gt; (Visual Basic)</span></span>
<span data-ttu-id="ab5d1-103">指定将显示在另请参阅部分的链接。</span><span class="sxs-lookup"><span data-stu-id="ab5d1-103">Specifies a link that appears in the See Also section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab5d1-104">语法</span><span class="sxs-lookup"><span data-stu-id="ab5d1-104">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ab5d1-105">参数</span><span class="sxs-lookup"><span data-stu-id="ab5d1-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="ab5d1-106">对可从当前编译环境调用的成员或字段的引用。</span><span class="sxs-lookup"><span data-stu-id="ab5d1-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="ab5d1-107">编译器会检查给定的代码元素存在，并将传递`member`为在输出 XML 中的元素名称。</span><span class="sxs-lookup"><span data-stu-id="ab5d1-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="ab5d1-108">`member` 必须出现在双引号 (" ") 内。</span><span class="sxs-lookup"><span data-stu-id="ab5d1-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ab5d1-109">备注</span><span class="sxs-lookup"><span data-stu-id="ab5d1-109">Remarks</span></span>  
 <span data-ttu-id="ab5d1-110">使用`<seealso>`标记指定你想要的另请参阅部分中显示的文本。</span><span class="sxs-lookup"><span data-stu-id="ab5d1-110">Use the `<seealso>` tag to specify the text that you want to appear in a See Also section.</span></span> <span data-ttu-id="ab5d1-111">使用 [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) 从文本内指定链接。</span><span class="sxs-lookup"><span data-stu-id="ab5d1-111">Use [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="ab5d1-112">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="ab5d1-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab5d1-113">示例</span><span class="sxs-lookup"><span data-stu-id="ab5d1-113">Example</span></span>  
 <span data-ttu-id="ab5d1-114">此示例使用`<seealso>`中标记`DoesRecordExist`备注部分来引用`UpdateRecord`方法。</span><span class="sxs-lookup"><span data-stu-id="ab5d1-114">This example uses the `<seealso>` tag in the `DoesRecordExist` remarks section to refer to the `UpdateRecord` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/seealso_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ab5d1-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="ab5d1-115">See Also</span></span>  
 [<span data-ttu-id="ab5d1-116">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="ab5d1-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
