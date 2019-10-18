---
title: <code> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: d4e887e3bbbc01e4cef5278f67b8c4afe273bf28
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524032"
---
# <a name="code-visual-basic"></a><span data-ttu-id="31ed0-101">\<code > （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="31ed0-101">\<code> (Visual Basic)</span></span>
<span data-ttu-id="31ed0-102">指示文本为多行代码。</span><span class="sxs-lookup"><span data-stu-id="31ed0-102">Indicates that the text is multiple lines of code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31ed0-103">语法</span><span class="sxs-lookup"><span data-stu-id="31ed0-103">Syntax</span></span>  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a><span data-ttu-id="31ed0-104">参数</span><span class="sxs-lookup"><span data-stu-id="31ed0-104">Parameters</span></span>  
 `content`  
 <span data-ttu-id="31ed0-105">要标记为代码的文本。</span><span class="sxs-lookup"><span data-stu-id="31ed0-105">The text to mark as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31ed0-106">备注</span><span class="sxs-lookup"><span data-stu-id="31ed0-106">Remarks</span></span>  
 <span data-ttu-id="31ed0-107">使用 `<code>` 标记将多行指示为代码。</span><span class="sxs-lookup"><span data-stu-id="31ed0-107">Use the `<code>` tag to indicate multiple lines as code.</span></span> <span data-ttu-id="31ed0-108">使用 [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) 指示应将说明内的文本标记为代码。</span><span class="sxs-lookup"><span data-stu-id="31ed0-108">Use [\<c>](../../../visual-basic/language-reference/xmldoc/c.md) to indicate that text within a description should be marked as code.</span></span>  
  
 <span data-ttu-id="31ed0-109">使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="31ed0-109">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31ed0-110">示例</span><span class="sxs-lookup"><span data-stu-id="31ed0-110">Example</span></span>  
 <span data-ttu-id="31ed0-111">此示例使用 \<code > 标记，包括使用 `ID` 字段的示例代码。</span><span class="sxs-lookup"><span data-stu-id="31ed0-111">This example uses the \<code> tag to include example code for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="31ed0-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="31ed0-112">See also</span></span>

- [<span data-ttu-id="31ed0-113">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="31ed0-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
