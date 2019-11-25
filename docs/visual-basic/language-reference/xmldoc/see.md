---
title: <see>
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: 3c149b8ff60bcc2aba06856ad95f461fb18da4b6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352231"
---
# <a name="see-visual-basic"></a><span data-ttu-id="93edf-101">\<see> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93edf-101">\<see> (Visual Basic)</span></span>
<span data-ttu-id="93edf-102">Specifies a link to another member.</span><span class="sxs-lookup"><span data-stu-id="93edf-102">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93edf-103">语法</span><span class="sxs-lookup"><span data-stu-id="93edf-103">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="93edf-104">参数</span><span class="sxs-lookup"><span data-stu-id="93edf-104">Parameters</span></span>  
 `member`  
 <span data-ttu-id="93edf-105">对可从当前编译环境调用的成员或字段的引用。</span><span class="sxs-lookup"><span data-stu-id="93edf-105">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="93edf-106">编译器检查是否存在给定的码位元素，并将 `member` 传递到输出 XML 中的元素名称。</span><span class="sxs-lookup"><span data-stu-id="93edf-106">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="93edf-107">`member` 必须出现在双引号 (" ") 内。</span><span class="sxs-lookup"><span data-stu-id="93edf-107">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93edf-108">备注</span><span class="sxs-lookup"><span data-stu-id="93edf-108">Remarks</span></span>  
 <span data-ttu-id="93edf-109">Use the `<see>` tag to specify a link from within text.</span><span class="sxs-lookup"><span data-stu-id="93edf-109">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="93edf-110">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span><span class="sxs-lookup"><span data-stu-id="93edf-110">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="93edf-111">使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="93edf-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="93edf-112">示例</span><span class="sxs-lookup"><span data-stu-id="93edf-112">Example</span></span>  
 <span data-ttu-id="93edf-113">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span><span class="sxs-lookup"><span data-stu-id="93edf-113">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="93edf-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="93edf-114">See also</span></span>

- [<span data-ttu-id="93edf-115">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="93edf-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
