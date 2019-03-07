---
title: <returns> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 670064084d3297a54b2860da3fe3acab00fa3ed8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57469178"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="3e513-102">\<返回 > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3e513-102">\<returns> (Visual Basic)</span></span>
<span data-ttu-id="3e513-103">指定属性或函数的返回值。</span><span class="sxs-lookup"><span data-stu-id="3e513-103">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e513-104">语法</span><span class="sxs-lookup"><span data-stu-id="3e513-104">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e513-105">参数</span><span class="sxs-lookup"><span data-stu-id="3e513-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="3e513-106">返回值的说明。</span><span class="sxs-lookup"><span data-stu-id="3e513-106">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e513-107">备注</span><span class="sxs-lookup"><span data-stu-id="3e513-107">Remarks</span></span>  
 <span data-ttu-id="3e513-108">使用`<returns>`标记来描述返回值的方法声明的注释中。</span><span class="sxs-lookup"><span data-stu-id="3e513-108">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="3e513-109">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="3e513-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e513-110">示例</span><span class="sxs-lookup"><span data-stu-id="3e513-110">Example</span></span>  
 <span data-ttu-id="3e513-111">此示例使用`<returns>`标记解释`DoesRecordExist`函数返回。</span><span class="sxs-lookup"><span data-stu-id="3e513-111">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="3e513-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e513-112">See also</span></span>
- [<span data-ttu-id="3e513-113">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="3e513-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
