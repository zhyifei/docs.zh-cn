---
title: <paramref> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 49ed974dabe747c383fa1ffa85371afecc4d2f5d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484272"
---
# <a name="paramref-visual-basic"></a><span data-ttu-id="d1d76-102">\<paramref > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d1d76-102">\<paramref> (Visual Basic)</span></span>
<span data-ttu-id="d1d76-103">将参数设置为一个单词。</span><span class="sxs-lookup"><span data-stu-id="d1d76-103">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1d76-104">语法</span><span class="sxs-lookup"><span data-stu-id="d1d76-104">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1d76-105">参数</span><span class="sxs-lookup"><span data-stu-id="d1d76-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="d1d76-106">要引用的参数的名称。</span><span class="sxs-lookup"><span data-stu-id="d1d76-106">The name of the parameter to refer to.</span></span> <span data-ttu-id="d1d76-107">用双引号 (" ") 将名称引起来。</span><span class="sxs-lookup"><span data-stu-id="d1d76-107">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1d76-108">备注</span><span class="sxs-lookup"><span data-stu-id="d1d76-108">Remarks</span></span>  
 <span data-ttu-id="d1d76-109">`<paramref>`标记为您提供了一种方法来指示 word 是一个参数。</span><span class="sxs-lookup"><span data-stu-id="d1d76-109">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="d1d76-110">可以处理 XML 文件以设置此参数的格式以不同的方式。</span><span class="sxs-lookup"><span data-stu-id="d1d76-110">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="d1d76-111">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="d1d76-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1d76-112">示例</span><span class="sxs-lookup"><span data-stu-id="d1d76-112">Example</span></span>  
 <span data-ttu-id="d1d76-113">此示例使用`<paramref>`标记来指代`id`参数。</span><span class="sxs-lookup"><span data-stu-id="d1d76-113">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="d1d76-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1d76-114">See also</span></span>
- [<span data-ttu-id="d1d76-115">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="d1d76-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
