---
title: '&lt;返回&gt;(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 47debcef2c6ce56fda4c4a0818c8e813b41ebad1
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925013"
---
# <a name="ltreturnsgt-visual-basic"></a><span data-ttu-id="56eb1-102">&lt;返回&gt;(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="56eb1-102">&lt;returns&gt; (Visual Basic)</span></span>
<span data-ttu-id="56eb1-103">指定属性或函数的返回值。</span><span class="sxs-lookup"><span data-stu-id="56eb1-103">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="56eb1-104">语法</span><span class="sxs-lookup"><span data-stu-id="56eb1-104">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="56eb1-105">参数</span><span class="sxs-lookup"><span data-stu-id="56eb1-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="56eb1-106">返回值的说明。</span><span class="sxs-lookup"><span data-stu-id="56eb1-106">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="56eb1-107">备注</span><span class="sxs-lookup"><span data-stu-id="56eb1-107">Remarks</span></span>  
 <span data-ttu-id="56eb1-108">使用`<returns>`标记来描述返回值的方法声明的注释中。</span><span class="sxs-lookup"><span data-stu-id="56eb1-108">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="56eb1-109">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="56eb1-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56eb1-110">示例</span><span class="sxs-lookup"><span data-stu-id="56eb1-110">Example</span></span>  
 <span data-ttu-id="56eb1-111">此示例使用`<returns>`标记解释`DoesRecordExist`函数返回。</span><span class="sxs-lookup"><span data-stu-id="56eb1-111">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/returns_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="56eb1-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="56eb1-112">See Also</span></span>  
 [<span data-ttu-id="56eb1-113">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="56eb1-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
