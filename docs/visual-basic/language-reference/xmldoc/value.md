---
title: <value> （Visual Basic）
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 516ff6ba534478d066b8ca06baee46bdd4b35265
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524606"
---
# <a name="value-visual-basic"></a><span data-ttu-id="c89ef-102">\<value > （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="c89ef-102">\<value> (Visual Basic)</span></span>
<span data-ttu-id="c89ef-103">指定属性的说明。</span><span class="sxs-lookup"><span data-stu-id="c89ef-103">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c89ef-104">语法</span><span class="sxs-lookup"><span data-stu-id="c89ef-104">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="c89ef-105">参数</span><span class="sxs-lookup"><span data-stu-id="c89ef-105">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="c89ef-106">属性的说明。</span><span class="sxs-lookup"><span data-stu-id="c89ef-106">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c89ef-107">备注</span><span class="sxs-lookup"><span data-stu-id="c89ef-107">Remarks</span></span>  
 <span data-ttu-id="c89ef-108">使用 `<value>` 标记来描述属性。</span><span class="sxs-lookup"><span data-stu-id="c89ef-108">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="c89ef-109">请注意，当您使用 Visual Studio 开发环境中的代码向导添加属性时，它将为新属性添加一个[\<summary >](../../../visual-basic/language-reference/xmldoc/summary.md)标记。</span><span class="sxs-lookup"><span data-stu-id="c89ef-109">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="c89ef-110">然后，你应该手动添加 `<value>` 标记来描述属性表示的值。</span><span class="sxs-lookup"><span data-stu-id="c89ef-110">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="c89ef-111">使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="c89ef-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c89ef-112">示例</span><span class="sxs-lookup"><span data-stu-id="c89ef-112">Example</span></span>  
 <span data-ttu-id="c89ef-113">此示例使用 `<value>` 标记来描述 `Counter` 属性包含的值。</span><span class="sxs-lookup"><span data-stu-id="c89ef-113">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c89ef-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c89ef-114">See also</span></span>

- [<span data-ttu-id="c89ef-115">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="c89ef-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
