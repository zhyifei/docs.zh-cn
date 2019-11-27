---
title: <example>
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 8f36ac1337dd0d1400180fbd3deae2bb24ad9c58
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348483"
---
# <a name="example-visual-basic"></a><span data-ttu-id="d7368-101">\<示例 > （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="d7368-101">\<example> (Visual Basic)</span></span>
<span data-ttu-id="d7368-102">指定成员的示例。</span><span class="sxs-lookup"><span data-stu-id="d7368-102">Specifies an example for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7368-103">语法</span><span class="sxs-lookup"><span data-stu-id="d7368-103">Syntax</span></span>  
  
```xml  
<example>description</example>  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7368-104">参数</span><span class="sxs-lookup"><span data-stu-id="d7368-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="d7368-105">代码示例的说明。</span><span class="sxs-lookup"><span data-stu-id="d7368-105">A description of the code sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7368-106">备注</span><span class="sxs-lookup"><span data-stu-id="d7368-106">Remarks</span></span>  
 <span data-ttu-id="d7368-107">`<example>` 标记可以指定如何使用方法或其他库成员的示例。</span><span class="sxs-lookup"><span data-stu-id="d7368-107">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="d7368-108">这通常涉及到使用 [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) 标记。</span><span class="sxs-lookup"><span data-stu-id="d7368-108">This commonly involves using the [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) tag.</span></span>  
  
 <span data-ttu-id="d7368-109">使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="d7368-109">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7368-110">示例</span><span class="sxs-lookup"><span data-stu-id="d7368-110">Example</span></span>  
 <span data-ttu-id="d7368-111">此示例使用 `<example>` 标记以包含使用 `ID` 字段的示例。</span><span class="sxs-lookup"><span data-stu-id="d7368-111">This example uses the `<example>` tag to include an example for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d7368-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7368-112">See also</span></span>

- [<span data-ttu-id="d7368-113">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="d7368-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
