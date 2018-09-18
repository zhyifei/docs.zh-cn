---
title: '&lt;异常&gt;(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <exception> XML tag
- exception XML tag
ms.assetid: c0517549-171e-4dae-ab88-a9c1700b6eee
ms.openlocfilehash: 047805ad91d87550da80448fd10883ae58647bd6
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "45969491"
---
# <a name="ltexceptiongt-visual-basic"></a><span data-ttu-id="d4dc6-102">&lt;异常&gt;(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d4dc6-102">&lt;exception&gt; (Visual Basic)</span></span>
<span data-ttu-id="d4dc6-103">指定可引发哪些异常。</span><span class="sxs-lookup"><span data-stu-id="d4dc6-103">Specifies which exceptions can be thrown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4dc6-104">语法</span><span class="sxs-lookup"><span data-stu-id="d4dc6-104">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d4dc6-105">参数</span><span class="sxs-lookup"><span data-stu-id="d4dc6-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="d4dc6-106">对当前编译环境中出现的一个异常的引用。</span><span class="sxs-lookup"><span data-stu-id="d4dc6-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="d4dc6-107">编译器检查是否存在给定的异常，并将 `member` 转换为输出 XML 中的规范的元素名称。</span><span class="sxs-lookup"><span data-stu-id="d4dc6-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="d4dc6-108">`member` 必须出现在双引号 (" ") 内。</span><span class="sxs-lookup"><span data-stu-id="d4dc6-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="d4dc6-109">描述。</span><span class="sxs-lookup"><span data-stu-id="d4dc6-109">A description.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4dc6-110">备注</span><span class="sxs-lookup"><span data-stu-id="d4dc6-110">Remarks</span></span>  
 <span data-ttu-id="d4dc6-111">使用`<exception>`标记来指定可以引发哪些异常。</span><span class="sxs-lookup"><span data-stu-id="d4dc6-111">Use the `<exception>` tag to specify which exceptions can be thrown.</span></span> <span data-ttu-id="d4dc6-112">这是适用于方法定义的标记。</span><span class="sxs-lookup"><span data-stu-id="d4dc6-112">This tag is applied to a method definition.</span></span>  
  
 <span data-ttu-id="d4dc6-113">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="d4dc6-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4dc6-114">示例</span><span class="sxs-lookup"><span data-stu-id="d4dc6-114">Example</span></span>  
 <span data-ttu-id="d4dc6-115">此示例使用`<exception>`标记来描述异常的`IntDivide`函数可以引发。</span><span class="sxs-lookup"><span data-stu-id="d4dc6-115">This example uses the `<exception>` tag to describe an exception that the `IntDivide` function can throw.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#3](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/exception_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="d4dc6-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="d4dc6-116">See Also</span></span>  
 [<span data-ttu-id="d4dc6-117">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="d4dc6-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
