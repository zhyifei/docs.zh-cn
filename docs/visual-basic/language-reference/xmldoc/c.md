---
title: <c> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 4ea19ed5330dcbb8fcd84708d1546a81d909b04e
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523939"
---
# <a name="c-visual-basic"></a><span data-ttu-id="39fc6-102">\<c > （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="39fc6-102">\<c> (Visual Basic)</span></span>
<span data-ttu-id="39fc6-103">指示说明中的文本为代码。</span><span class="sxs-lookup"><span data-stu-id="39fc6-103">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39fc6-104">语法</span><span class="sxs-lookup"><span data-stu-id="39fc6-104">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="39fc6-105">参数</span><span class="sxs-lookup"><span data-stu-id="39fc6-105">Parameters</span></span>  
  
|<span data-ttu-id="39fc6-106">参数</span><span class="sxs-lookup"><span data-stu-id="39fc6-106">Parameter</span></span>|<span data-ttu-id="39fc6-107">描述</span><span class="sxs-lookup"><span data-stu-id="39fc6-107">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="39fc6-108">要指示为代码的文本。</span><span class="sxs-lookup"><span data-stu-id="39fc6-108">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39fc6-109">备注</span><span class="sxs-lookup"><span data-stu-id="39fc6-109">Remarks</span></span>  
 <span data-ttu-id="39fc6-110">@No__t_0 标记提供了一种方法，用于指示应将说明中的文本标记为代码。</span><span class="sxs-lookup"><span data-stu-id="39fc6-110">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="39fc6-111">使用 [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) 指示作为代码的多行文本。</span><span class="sxs-lookup"><span data-stu-id="39fc6-111">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="39fc6-112">使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="39fc6-112">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="39fc6-113">示例</span><span class="sxs-lookup"><span data-stu-id="39fc6-113">Example</span></span>  
 <span data-ttu-id="39fc6-114">此示例使用 summary 节中的 `<c>` 标记来指示 `Counter` 为代码。</span><span class="sxs-lookup"><span data-stu-id="39fc6-114">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="39fc6-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="39fc6-115">See also</span></span>

- [<span data-ttu-id="39fc6-116">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="39fc6-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
