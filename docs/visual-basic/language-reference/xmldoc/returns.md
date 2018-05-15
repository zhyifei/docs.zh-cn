---
title: '&lt;返回&gt;(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: effc55bd65ae6c54575b7931529499505a9523cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="ltreturnsgt-visual-basic"></a><span data-ttu-id="5ac28-102">&lt;返回&gt;(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ac28-102">&lt;returns&gt; (Visual Basic)</span></span>
<span data-ttu-id="5ac28-103">指定的属性或函数的返回值。</span><span class="sxs-lookup"><span data-stu-id="5ac28-103">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ac28-104">语法</span><span class="sxs-lookup"><span data-stu-id="5ac28-104">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5ac28-105">参数</span><span class="sxs-lookup"><span data-stu-id="5ac28-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="5ac28-106">返回值的说明。</span><span class="sxs-lookup"><span data-stu-id="5ac28-106">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ac28-107">备注</span><span class="sxs-lookup"><span data-stu-id="5ac28-107">Remarks</span></span>  
 <span data-ttu-id="5ac28-108">使用`<returns>`方法声明来描述返回的值的注释中的标记。</span><span class="sxs-lookup"><span data-stu-id="5ac28-108">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="5ac28-109">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="5ac28-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ac28-110">示例</span><span class="sxs-lookup"><span data-stu-id="5ac28-110">Example</span></span>  
 <span data-ttu-id="5ac28-111">此示例使用`<returns>`标记解释`DoesRecordExist`函数返回。</span><span class="sxs-lookup"><span data-stu-id="5ac28-111">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/returns_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="5ac28-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ac28-112">See Also</span></span>  
 [<span data-ttu-id="5ac28-113">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="5ac28-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
