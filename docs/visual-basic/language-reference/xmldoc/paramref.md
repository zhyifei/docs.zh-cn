---
title: <paramref> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 85171bd8deeb5f54c4560bb8b2339107bb8d8c68
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524706"
---
# <a name="paramref-visual-basic"></a><span data-ttu-id="d215b-102">\<paramref > （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="d215b-102">\<paramref> (Visual Basic)</span></span>
<span data-ttu-id="d215b-103">将单词设置为参数格式。</span><span class="sxs-lookup"><span data-stu-id="d215b-103">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d215b-104">语法</span><span class="sxs-lookup"><span data-stu-id="d215b-104">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="d215b-105">参数</span><span class="sxs-lookup"><span data-stu-id="d215b-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="d215b-106">要引用的参数的名称。</span><span class="sxs-lookup"><span data-stu-id="d215b-106">The name of the parameter to refer to.</span></span> <span data-ttu-id="d215b-107">用双引号 (" ") 将名称引起来。</span><span class="sxs-lookup"><span data-stu-id="d215b-107">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d215b-108">备注</span><span class="sxs-lookup"><span data-stu-id="d215b-108">Remarks</span></span>  
 <span data-ttu-id="d215b-109">@No__t_0 标记为你提供了一种方法，用于指示某个字是一个参数。</span><span class="sxs-lookup"><span data-stu-id="d215b-109">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="d215b-110">可以处理 XML 文件，以便以某种不同的方式格式化此参数。</span><span class="sxs-lookup"><span data-stu-id="d215b-110">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="d215b-111">使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="d215b-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d215b-112">示例</span><span class="sxs-lookup"><span data-stu-id="d215b-112">Example</span></span>  
 <span data-ttu-id="d215b-113">此示例使用 `<paramref>` 标记来引用 `id` 参数。</span><span class="sxs-lookup"><span data-stu-id="d215b-113">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="d215b-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d215b-114">See also</span></span>

- [<span data-ttu-id="d215b-115">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="d215b-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
