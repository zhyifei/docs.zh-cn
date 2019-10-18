---
title: <see> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- see XML tag
- <see> XML tag
ms.assetid: 7e18f60b-ef4a-4678-a797-5eb918635ca9
ms.openlocfilehash: e3ae5fb63540e47e5b8da2e2d60d5bd736e019d7
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524657"
---
# <a name="see-visual-basic"></a><span data-ttu-id="6c752-102">\<see > （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="6c752-102">\<see> (Visual Basic)</span></span>
<span data-ttu-id="6c752-103">指定指向另一个成员的链接。</span><span class="sxs-lookup"><span data-stu-id="6c752-103">Specifies a link to another member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c752-104">语法</span><span class="sxs-lookup"><span data-stu-id="6c752-104">Syntax</span></span>  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c752-105">参数</span><span class="sxs-lookup"><span data-stu-id="6c752-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="6c752-106">对可从当前编译环境调用的成员或字段的引用。</span><span class="sxs-lookup"><span data-stu-id="6c752-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="6c752-107">编译器检查是否存在给定的码位元素，并将 `member` 传递到输出 XML 中的元素名称。</span><span class="sxs-lookup"><span data-stu-id="6c752-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.</span></span> <span data-ttu-id="6c752-108">`member` 必须出现在双引号 (" ") 内。</span><span class="sxs-lookup"><span data-stu-id="6c752-108">`member` must appear within double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c752-109">备注</span><span class="sxs-lookup"><span data-stu-id="6c752-109">Remarks</span></span>  
 <span data-ttu-id="6c752-110">使用 `<see>` 标记指定文本中的链接。</span><span class="sxs-lookup"><span data-stu-id="6c752-110">Use the `<see>` tag to specify a link from within text.</span></span> <span data-ttu-id="6c752-111">使用[\<seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md)来指示你可能希望在 "另请参阅" 部分中显示的文本。</span><span class="sxs-lookup"><span data-stu-id="6c752-111">Use [\<seealso>](../../../visual-basic/language-reference/xmldoc/seealso.md) to indicate text that you might want to appear in a "See Also" section.</span></span>  
  
 <span data-ttu-id="6c752-112">使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="6c752-112">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c752-113">示例</span><span class="sxs-lookup"><span data-stu-id="6c752-113">Example</span></span>  
 <span data-ttu-id="6c752-114">此示例使用 `UpdateRecord` 备注 "部分中的 `<see>` 标记来引用 `DoesRecordExist` 方法。</span><span class="sxs-lookup"><span data-stu-id="6c752-114">This example uses the `<see>` tag in the `UpdateRecord` remarks section to refer to the `DoesRecordExist` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="6c752-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="6c752-115">See also</span></span>

- [<span data-ttu-id="6c752-116">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="6c752-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
