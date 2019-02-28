---
title: <exception> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: 157287ce5c85ec51f1711934cf9a5e4f568957ef
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977173"
---
# <a name="exception-visual-basic"></a><span data-ttu-id="b9204-102">\<异常 > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b9204-102">\<exception> (Visual Basic)</span></span>
<span data-ttu-id="b9204-103">指定可引发哪些异常。</span><span class="sxs-lookup"><span data-stu-id="b9204-103">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9204-104">语法</span><span class="sxs-lookup"><span data-stu-id="b9204-104">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9204-105">参数</span><span class="sxs-lookup"><span data-stu-id="b9204-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="b9204-106">对当前编译环境中出现的一个异常的引用。</span><span class="sxs-lookup"><span data-stu-id="b9204-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="b9204-107">编译器检查是否存在给定的异常，并将 `member` 转换为输出 XML 中的规范的元素名称。</span><span class="sxs-lookup"><span data-stu-id="b9204-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="b9204-108">`member` 必须出现在双引号 (" ") 内。</span><span class="sxs-lookup"><span data-stu-id="b9204-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="b9204-109">描述。</span><span class="sxs-lookup"><span data-stu-id="b9204-109">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9204-110">备注</span><span class="sxs-lookup"><span data-stu-id="b9204-110">Remarks</span></span>  
 <span data-ttu-id="b9204-111">使用`<exception>`标记来指定可以引发哪些异常。</span><span class="sxs-lookup"><span data-stu-id="b9204-111">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="b9204-112">这是适用于方法定义的标记。</span><span class="sxs-lookup"><span data-stu-id="b9204-112">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="b9204-113">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="b9204-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9204-114">示例</span><span class="sxs-lookup"><span data-stu-id="b9204-114">Example</span></span>  
 <span data-ttu-id="b9204-115">此示例使用`<exception>`标记来描述异常的`IntDivide`函数可以引发。</span><span class="sxs-lookup"><span data-stu-id="b9204-115">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="b9204-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9204-116">See also</span></span>
- [<span data-ttu-id="b9204-117">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="b9204-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
