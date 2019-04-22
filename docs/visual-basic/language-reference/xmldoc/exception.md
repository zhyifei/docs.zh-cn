---
title: <exception> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: 4e2f441863d6a8677593a257cdb2cc841634d47c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58820236"
---
# <a name="exception-visual-basic"></a><span data-ttu-id="c525a-102">\<异常 > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c525a-102">\<exception> (Visual Basic)</span></span>
<span data-ttu-id="c525a-103">指定可引发哪些异常。</span><span class="sxs-lookup"><span data-stu-id="c525a-103">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c525a-104">语法</span><span class="sxs-lookup"><span data-stu-id="c525a-104">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a><span data-ttu-id="c525a-105">参数</span><span class="sxs-lookup"><span data-stu-id="c525a-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="c525a-106">对当前编译环境中出现的一个异常的引用。</span><span class="sxs-lookup"><span data-stu-id="c525a-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="c525a-107">编译器检查是否存在给定的异常，并将 `member` 转换为输出 XML 中的规范的元素名称。</span><span class="sxs-lookup"><span data-stu-id="c525a-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="c525a-108">`member` 必须出现在双引号 (" ") 内。</span><span class="sxs-lookup"><span data-stu-id="c525a-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="c525a-109">描述。</span><span class="sxs-lookup"><span data-stu-id="c525a-109">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c525a-110">备注</span><span class="sxs-lookup"><span data-stu-id="c525a-110">Remarks</span></span>  
 <span data-ttu-id="c525a-111">使用`<exception>`标记来指定可以引发哪些异常。</span><span class="sxs-lookup"><span data-stu-id="c525a-111">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="c525a-112">这是适用于方法定义的标记。</span><span class="sxs-lookup"><span data-stu-id="c525a-112">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="c525a-113">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="c525a-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c525a-114">示例</span><span class="sxs-lookup"><span data-stu-id="c525a-114">Example</span></span>  
 <span data-ttu-id="c525a-115">此示例使用`<exception>`标记来描述异常的`IntDivide`函数可以引发。</span><span class="sxs-lookup"><span data-stu-id="c525a-115">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="c525a-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="c525a-116">See also</span></span>

- [<span data-ttu-id="c525a-117">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="c525a-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
