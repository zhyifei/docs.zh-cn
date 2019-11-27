---
title: <c>
ms.date: 07/20/2015
helpviewer_keywords:
- c XML tag
- <c> XML tag
ms.assetid: 36ad5d1b-11f7-4012-8932-41962ac327d1
ms.openlocfilehash: 857ea1ccca4d74daf65bba03845004561afefd55
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348513"
---
# <a name="c-visual-basic"></a><span data-ttu-id="e76cc-101">\<c > （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="e76cc-101">\<c> (Visual Basic)</span></span>
<span data-ttu-id="e76cc-102">指示说明中的文本为代码。</span><span class="sxs-lookup"><span data-stu-id="e76cc-102">Indicates that text within a description is code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e76cc-103">语法</span><span class="sxs-lookup"><span data-stu-id="e76cc-103">Syntax</span></span>  
  
```xml  
<c>text</c>  
```  
  
## <a name="parameters"></a><span data-ttu-id="e76cc-104">参数</span><span class="sxs-lookup"><span data-stu-id="e76cc-104">Parameters</span></span>  
  
|<span data-ttu-id="e76cc-105">参数</span><span class="sxs-lookup"><span data-stu-id="e76cc-105">Parameter</span></span>|<span data-ttu-id="e76cc-106">说明</span><span class="sxs-lookup"><span data-stu-id="e76cc-106">Description</span></span>|  
|---|---|  
|`text`|<span data-ttu-id="e76cc-107">要指示为代码的文本。</span><span class="sxs-lookup"><span data-stu-id="e76cc-107">The text you would like to indicate as code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e76cc-108">备注</span><span class="sxs-lookup"><span data-stu-id="e76cc-108">Remarks</span></span>  
 <span data-ttu-id="e76cc-109">`<c>` 标记提供了一种方法，用于指示应将说明中的文本标记为代码。</span><span class="sxs-lookup"><span data-stu-id="e76cc-109">The `<c>` tag gives you a way to indicate that text within a description should be marked as code.</span></span> <span data-ttu-id="e76cc-110">使用 [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) 指示作为代码的多行文本。</span><span class="sxs-lookup"><span data-stu-id="e76cc-110">Use [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) to indicate multiple lines as code.</span></span>  
  
 <span data-ttu-id="e76cc-111">使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="e76cc-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e76cc-112">示例</span><span class="sxs-lookup"><span data-stu-id="e76cc-112">Example</span></span>  
 <span data-ttu-id="e76cc-113">此示例使用 summary 节中的 `<c>` 标记来指示 `Counter` 为代码。</span><span class="sxs-lookup"><span data-stu-id="e76cc-113">This example uses the `<c>` tag in the summary section to indicate that `Counter` is code.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="e76cc-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e76cc-114">See also</span></span>

- [<span data-ttu-id="e76cc-115">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="e76cc-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
