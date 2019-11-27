---
title: <seealso>
ms.date: 07/20/2015
helpviewer_keywords:
- <seealso> XML tag
- seealso XML tag
ms.assetid: 36050c95-1af2-4284-b9b6-1a70691ed978
ms.openlocfilehash: 27bb2c271631170082709d9e3d76cd39eefbc860
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352216"
---
# <a name="seealso-visual-basic"></a><span data-ttu-id="9d426-101">\<seealso > （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="9d426-101">\<seealso> (Visual Basic)</span></span>
<span data-ttu-id="9d426-102">指定显示在 "另请参见" 部分中的链接。</span><span class="sxs-lookup"><span data-stu-id="9d426-102">Specifies a link that appears in the See Also section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d426-103">语法</span><span class="sxs-lookup"><span data-stu-id="9d426-103">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d426-104">参数</span><span class="sxs-lookup"><span data-stu-id="9d426-104">Parameters</span></span>  
 `member`  
 <span data-ttu-id="9d426-105">对可从当前编译环境调用的成员或字段的引用。</span><span class="sxs-lookup"><span data-stu-id="9d426-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="9d426-106">编译器检查是否存在给定的码位元素，并将 `member` 传递到输出 XML 中的元素名称。</span><span class="sxs-lookup"><span data-stu-id="9d426-106">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="9d426-107">`member` 必须出现在双引号 (" ") 内。</span><span class="sxs-lookup"><span data-stu-id="9d426-107">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9d426-108">备注</span><span class="sxs-lookup"><span data-stu-id="9d426-108">Remarks</span></span>  
 <span data-ttu-id="9d426-109">使用 `<seealso>` 标记来指定要在 "另请参见" 部分中显示的文本。</span><span class="sxs-lookup"><span data-stu-id="9d426-109">Use the `<seealso>` tag to specify the text that you want to appear in a See Also section.</span></span> <span data-ttu-id="9d426-110">使用 [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) 从文本内指定链接。</span><span class="sxs-lookup"><span data-stu-id="9d426-110">Use [\<see>](../../../visual-basic/language-reference/xmldoc/see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="9d426-111">使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="9d426-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d426-112">示例</span><span class="sxs-lookup"><span data-stu-id="9d426-112">Example</span></span>  
 <span data-ttu-id="9d426-113">此示例使用 `DoesRecordExist` 备注 "部分中的 `<seealso>` 标记来引用 `UpdateRecord` 方法。</span><span class="sxs-lookup"><span data-stu-id="9d426-113">This example uses the `<seealso>` tag in the `DoesRecordExist` remarks section to refer to the `UpdateRecord` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="9d426-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9d426-114">See also</span></span>

- [<span data-ttu-id="9d426-115">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="9d426-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
