---
title: '&lt;typeparam&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: 76e0e8d4757f29bb5df82ea1482beff3dd43c0e4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33598009"
---
# <a name="lttypeparamgt-visual-basic"></a><span data-ttu-id="ecc6a-102">&lt;typeparam&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ecc6a-102">&lt;typeparam&gt; (Visual Basic)</span></span>
<span data-ttu-id="ecc6a-103">定义的类型参数的名称和描述。</span><span class="sxs-lookup"><span data-stu-id="ecc6a-103">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecc6a-104">语法</span><span class="sxs-lookup"><span data-stu-id="ecc6a-104">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ecc6a-105">参数</span><span class="sxs-lookup"><span data-stu-id="ecc6a-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="ecc6a-106">类型参数的名称。</span><span class="sxs-lookup"><span data-stu-id="ecc6a-106">The name of the type parameter.</span></span> <span data-ttu-id="ecc6a-107">用双引号 (" ") 将名称引起来。</span><span class="sxs-lookup"><span data-stu-id="ecc6a-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="ecc6a-108">类型参数的说明。</span><span class="sxs-lookup"><span data-stu-id="ecc6a-108">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ecc6a-109">备注</span><span class="sxs-lookup"><span data-stu-id="ecc6a-109">Remarks</span></span>  
 <span data-ttu-id="ecc6a-110">使用`<typeparam>`用于泛型类型或泛型成员声明以描述一个类型参数的注释中的标记。</span><span class="sxs-lookup"><span data-stu-id="ecc6a-110">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="ecc6a-111">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="ecc6a-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ecc6a-112">示例</span><span class="sxs-lookup"><span data-stu-id="ecc6a-112">Example</span></span>  
 <span data-ttu-id="ecc6a-113">此示例使用`<typeparam>`标记来描述`id`参数。</span><span class="sxs-lookup"><span data-stu-id="ecc6a-113">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/typeparam_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="ecc6a-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="ecc6a-114">See Also</span></span>  
 [<span data-ttu-id="ecc6a-115">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="ecc6a-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
