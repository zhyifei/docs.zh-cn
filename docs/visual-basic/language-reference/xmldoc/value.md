---
title: <value> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 2938d485bf6c547c792431b93fc8959c9c36befa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940733"
---
# <a name="value-visual-basic"></a><span data-ttu-id="8c89d-102">\<值 > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8c89d-102">\<value> (Visual Basic)</span></span>
<span data-ttu-id="8c89d-103">指定属性的说明。</span><span class="sxs-lookup"><span data-stu-id="8c89d-103">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c89d-104">语法</span><span class="sxs-lookup"><span data-stu-id="8c89d-104">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c89d-105">参数</span><span class="sxs-lookup"><span data-stu-id="8c89d-105">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="8c89d-106">属性的说明。</span><span class="sxs-lookup"><span data-stu-id="8c89d-106">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8c89d-107">备注</span><span class="sxs-lookup"><span data-stu-id="8c89d-107">Remarks</span></span>  
 <span data-ttu-id="8c89d-108">使用`<value>`标记描述的属性。</span><span class="sxs-lookup"><span data-stu-id="8c89d-108">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="8c89d-109">请注意，当添加在 Visual Studio 开发环境中使用代码向导的属性时，它将添加[\<摘要 >](../../../visual-basic/language-reference/xmldoc/summary.md)标记为新属性。</span><span class="sxs-lookup"><span data-stu-id="8c89d-109">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="8c89d-110">然后，应手动添加`<value>`标记来描述该属性表示的值。</span><span class="sxs-lookup"><span data-stu-id="8c89d-110">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="8c89d-111">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="8c89d-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c89d-112">示例</span><span class="sxs-lookup"><span data-stu-id="8c89d-112">Example</span></span>  
 <span data-ttu-id="8c89d-113">此示例使用`<value>`标记来描述哪些值`Counter`属性保存。</span><span class="sxs-lookup"><span data-stu-id="8c89d-113">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="8c89d-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c89d-114">See also</span></span>

- [<span data-ttu-id="8c89d-115">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="8c89d-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
