---
title: <value>
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 240c2131179420834e6dade729ee631c0d7811a4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352174"
---
# <a name="value-visual-basic"></a><span data-ttu-id="a1c76-101">\<值 > （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="a1c76-101">\<value> (Visual Basic)</span></span>
<span data-ttu-id="a1c76-102">指定属性的说明。</span><span class="sxs-lookup"><span data-stu-id="a1c76-102">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1c76-103">语法</span><span class="sxs-lookup"><span data-stu-id="a1c76-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="a1c76-104">参数</span><span class="sxs-lookup"><span data-stu-id="a1c76-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="a1c76-105">属性的说明。</span><span class="sxs-lookup"><span data-stu-id="a1c76-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1c76-106">备注</span><span class="sxs-lookup"><span data-stu-id="a1c76-106">Remarks</span></span>  
 <span data-ttu-id="a1c76-107">使用 `<value>` 标记来描述属性。</span><span class="sxs-lookup"><span data-stu-id="a1c76-107">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="a1c76-108">请注意，当你使用 Visual Studio 开发环境中的代码向导添加属性时，它将为新属性添加[\<摘要 >](../../../visual-basic/language-reference/xmldoc/summary.md)标记。</span><span class="sxs-lookup"><span data-stu-id="a1c76-108">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="a1c76-109">然后，你应该手动添加 `<value>` 标记来描述属性表示的值。</span><span class="sxs-lookup"><span data-stu-id="a1c76-109">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="a1c76-110">使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="a1c76-110">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a1c76-111">示例</span><span class="sxs-lookup"><span data-stu-id="a1c76-111">Example</span></span>  
 <span data-ttu-id="a1c76-112">此示例使用 `<value>` 标记来描述 `Counter` 属性包含的值。</span><span class="sxs-lookup"><span data-stu-id="a1c76-112">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="a1c76-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1c76-113">See also</span></span>

- [<span data-ttu-id="a1c76-114">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="a1c76-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
