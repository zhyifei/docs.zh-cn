---
title: '&lt;摘要&gt;(Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 5ef9b7a98503ff36174de4418ca7d599c365f5aa
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2018
ms.locfileid: "45593773"
---
# <a name="ltsummarygt-visual-basic"></a><span data-ttu-id="6f3eb-102">&lt;摘要&gt;(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6f3eb-102">&lt;summary&gt; (Visual Basic)</span></span>
<span data-ttu-id="6f3eb-103">指定的成员的摘要。</span><span class="sxs-lookup"><span data-stu-id="6f3eb-103">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f3eb-104">语法</span><span class="sxs-lookup"><span data-stu-id="6f3eb-104">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6f3eb-105">参数</span><span class="sxs-lookup"><span data-stu-id="6f3eb-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="6f3eb-106">对象的摘要。</span><span class="sxs-lookup"><span data-stu-id="6f3eb-106">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f3eb-107">备注</span><span class="sxs-lookup"><span data-stu-id="6f3eb-107">Remarks</span></span>  
 <span data-ttu-id="6f3eb-108">使用`<summary>`标记来描述类型或类型成员。</span><span class="sxs-lookup"><span data-stu-id="6f3eb-108">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="6f3eb-109">使用 [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) 可针对某个类型说明添加补充信息。</span><span class="sxs-lookup"><span data-stu-id="6f3eb-109">Use [\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="6f3eb-110">文本`<summary>`标记是在 IntelliSense 中，类型信息的唯一源，并还会显示在对象浏览器。</span><span class="sxs-lookup"><span data-stu-id="6f3eb-110">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="6f3eb-111">对象浏览器有关的信息，请参阅[查看代码结构](/visualstudio/ide/viewing-the-structure-of-code)。</span><span class="sxs-lookup"><span data-stu-id="6f3eb-111">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="6f3eb-112">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="6f3eb-112">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f3eb-113">示例</span><span class="sxs-lookup"><span data-stu-id="6f3eb-113">Example</span></span>  
 <span data-ttu-id="6f3eb-114">此示例使用`<summary>`标记来描述`ResetCounter`方法和`Counter`属性。</span><span class="sxs-lookup"><span data-stu-id="6f3eb-114">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/summary_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="6f3eb-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="6f3eb-115">See Also</span></span>  
 [<span data-ttu-id="6f3eb-116">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="6f3eb-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
