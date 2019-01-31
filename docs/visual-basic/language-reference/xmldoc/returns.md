---
title: <returns> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 0463d1b489fdad5e6af2d8eb20a1e68c77f57b4d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254959"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="04ca8-102">\<返回 > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04ca8-102">\<returns> (Visual Basic)</span></span>
<span data-ttu-id="04ca8-103">指定属性或函数的返回值。</span><span class="sxs-lookup"><span data-stu-id="04ca8-103">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04ca8-104">语法</span><span class="sxs-lookup"><span data-stu-id="04ca8-104">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="04ca8-105">参数</span><span class="sxs-lookup"><span data-stu-id="04ca8-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="04ca8-106">返回值的说明。</span><span class="sxs-lookup"><span data-stu-id="04ca8-106">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="04ca8-107">备注</span><span class="sxs-lookup"><span data-stu-id="04ca8-107">Remarks</span></span>  
 <span data-ttu-id="04ca8-108">使用`<returns>`标记来描述返回值的方法声明的注释中。</span><span class="sxs-lookup"><span data-stu-id="04ca8-108">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="04ca8-109">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="04ca8-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04ca8-110">示例</span><span class="sxs-lookup"><span data-stu-id="04ca8-110">Example</span></span>  
 <span data-ttu-id="04ca8-111">此示例使用`<returns>`标记解释`DoesRecordExist`函数返回。</span><span class="sxs-lookup"><span data-stu-id="04ca8-111">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/returns_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="04ca8-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="04ca8-112">See also</span></span>
- [<span data-ttu-id="04ca8-113">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="04ca8-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
