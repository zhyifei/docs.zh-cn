---
title: <example> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: a1dea0bcc40de8dea986e93a25617f607383ec21
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969214"
---
# <a name="example-visual-basic"></a><span data-ttu-id="ae63e-102">\<示例 > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae63e-102">\<example> (Visual Basic)</span></span>
<span data-ttu-id="ae63e-103">指定成员的一个示例。</span><span class="sxs-lookup"><span data-stu-id="ae63e-103">Specifies an example for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae63e-104">语法</span><span class="sxs-lookup"><span data-stu-id="ae63e-104">Syntax</span></span>  
  
```xml  
<example>description</example>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae63e-105">参数</span><span class="sxs-lookup"><span data-stu-id="ae63e-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="ae63e-106">代码示例的说明。</span><span class="sxs-lookup"><span data-stu-id="ae63e-106">A description of the code sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae63e-107">备注</span><span class="sxs-lookup"><span data-stu-id="ae63e-107">Remarks</span></span>  
 <span data-ttu-id="ae63e-108">`<example>`标记，可以指定如何使用方法或其他库成员的示例。</span><span class="sxs-lookup"><span data-stu-id="ae63e-108">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="ae63e-109">这通常涉及到使用 [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) 标记。</span><span class="sxs-lookup"><span data-stu-id="ae63e-109">This commonly involves using the [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) tag.</span></span>  
  
 <span data-ttu-id="ae63e-110">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="ae63e-110">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae63e-111">示例</span><span class="sxs-lookup"><span data-stu-id="ae63e-111">Example</span></span>  
 <span data-ttu-id="ae63e-112">此示例使用`<example>`标记包含有关使用示例`ID`字段。</span><span class="sxs-lookup"><span data-stu-id="ae63e-112">This example uses the `<example>` tag to include an example for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="ae63e-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae63e-113">See also</span></span>
- [<span data-ttu-id="ae63e-114">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="ae63e-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
