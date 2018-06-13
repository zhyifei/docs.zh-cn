---
title: '&lt;值&gt;(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: f33a4ec32b45d8996bd39f0cc49097b5fd9252e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602453"
---
# <a name="ltvaluegt-visual-basic"></a><span data-ttu-id="88f5e-102">&lt;值&gt;(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="88f5e-102">&lt;value&gt; (Visual Basic)</span></span>
<span data-ttu-id="88f5e-103">指定属性的说明。</span><span class="sxs-lookup"><span data-stu-id="88f5e-103">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88f5e-104">语法</span><span class="sxs-lookup"><span data-stu-id="88f5e-104">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="88f5e-105">参数</span><span class="sxs-lookup"><span data-stu-id="88f5e-105">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="88f5e-106">属性的说明。</span><span class="sxs-lookup"><span data-stu-id="88f5e-106">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="88f5e-107">备注</span><span class="sxs-lookup"><span data-stu-id="88f5e-107">Remarks</span></span>  
 <span data-ttu-id="88f5e-108">使用`<value>`标记来描述属性。</span><span class="sxs-lookup"><span data-stu-id="88f5e-108">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="88f5e-109">请注意，当你添加在 Visual Studio 开发环境中使用代码向导某个属性，它将添加[\<摘要 >](../../../visual-basic/language-reference/xmldoc/summary.md)标记为新的属性。</span><span class="sxs-lookup"><span data-stu-id="88f5e-109">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="88f5e-110">然后，应手动添加`<value>`标记来描述该属性表示的值。</span><span class="sxs-lookup"><span data-stu-id="88f5e-110">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="88f5e-111">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="88f5e-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="88f5e-112">示例</span><span class="sxs-lookup"><span data-stu-id="88f5e-112">Example</span></span>  
 <span data-ttu-id="88f5e-113">此示例使用`<value>`标记来描述哪些值`Counter`属性包含。</span><span class="sxs-lookup"><span data-stu-id="88f5e-113">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/value_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="88f5e-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="88f5e-114">See Also</span></span>  
 [<span data-ttu-id="88f5e-115">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="88f5e-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
