---
title: <summary> （Visual Basic）
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 25a0b307756401bed4d4c77d3668c2af53ba8b42
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524630"
---
# <a name="summary-visual-basic"></a><span data-ttu-id="ebf64-102">\<summary > （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="ebf64-102">\<summary> (Visual Basic)</span></span>
<span data-ttu-id="ebf64-103">指定成员的摘要。</span><span class="sxs-lookup"><span data-stu-id="ebf64-103">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebf64-104">语法</span><span class="sxs-lookup"><span data-stu-id="ebf64-104">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebf64-105">参数</span><span class="sxs-lookup"><span data-stu-id="ebf64-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="ebf64-106">对象的摘要。</span><span class="sxs-lookup"><span data-stu-id="ebf64-106">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ebf64-107">备注</span><span class="sxs-lookup"><span data-stu-id="ebf64-107">Remarks</span></span>  
 <span data-ttu-id="ebf64-108">使用 `<summary>` 标记来描述类型或类型成员。</span><span class="sxs-lookup"><span data-stu-id="ebf64-108">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="ebf64-109">使用 [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) 可针对某个类型说明添加补充信息。</span><span class="sxs-lookup"><span data-stu-id="ebf64-109">Use [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="ebf64-110">@No__t_0 标记的文本是 IntelliSense 中类型的唯一信息源，也显示在对象浏览器中。</span><span class="sxs-lookup"><span data-stu-id="ebf64-110">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="ebf64-111">有关对象浏览器的信息，请参阅[查看代码的结构](/visualstudio/ide/viewing-the-structure-of-code)。</span><span class="sxs-lookup"><span data-stu-id="ebf64-111">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="ebf64-112">使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="ebf64-112">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebf64-113">示例</span><span class="sxs-lookup"><span data-stu-id="ebf64-113">Example</span></span>  
 <span data-ttu-id="ebf64-114">此示例使用 `<summary>` 标记来描述 `ResetCounter` 方法和 `Counter` 属性。</span><span class="sxs-lookup"><span data-stu-id="ebf64-114">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="ebf64-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="ebf64-115">See also</span></span>

- [<span data-ttu-id="ebf64-116">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="ebf64-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
