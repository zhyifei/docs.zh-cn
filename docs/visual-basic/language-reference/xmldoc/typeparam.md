---
title: '&lt;typeparam&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: 73ffb1319e6724a13a80b3cd1ca6985e4cbac05c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54567056"
---
# <a name="lttypeparamgt-visual-basic"></a><span data-ttu-id="a2cf4-102">&lt;typeparam&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2cf4-102">&lt;typeparam&gt; (Visual Basic)</span></span>
<span data-ttu-id="a2cf4-103">定义的类型参数名称和说明。</span><span class="sxs-lookup"><span data-stu-id="a2cf4-103">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2cf4-104">语法</span><span class="sxs-lookup"><span data-stu-id="a2cf4-104">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a2cf4-105">参数</span><span class="sxs-lookup"><span data-stu-id="a2cf4-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="a2cf4-106">类型参数的名称。</span><span class="sxs-lookup"><span data-stu-id="a2cf4-106">The name of the type parameter.</span></span> <span data-ttu-id="a2cf4-107">用双引号 (" ") 将名称引起来。</span><span class="sxs-lookup"><span data-stu-id="a2cf4-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="a2cf4-108">类型参数的说明。</span><span class="sxs-lookup"><span data-stu-id="a2cf4-108">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2cf4-109">备注</span><span class="sxs-lookup"><span data-stu-id="a2cf4-109">Remarks</span></span>  
 <span data-ttu-id="a2cf4-110">使用`<typeparam>`的注释以描述一个类型参数的泛型类型或泛型成员声明中的标记。</span><span class="sxs-lookup"><span data-stu-id="a2cf4-110">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="a2cf4-111">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="a2cf4-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2cf4-112">示例</span><span class="sxs-lookup"><span data-stu-id="a2cf4-112">Example</span></span>  
 <span data-ttu-id="a2cf4-113">此示例使用`<typeparam>`标记来描述`id`参数。</span><span class="sxs-lookup"><span data-stu-id="a2cf4-113">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/typeparam_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="a2cf4-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2cf4-114">See also</span></span>
- [<span data-ttu-id="a2cf4-115">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="a2cf4-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
