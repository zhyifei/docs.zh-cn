---
title: <param>
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: 4405fdf2defbb27aa2146d20083fd406d1f07236
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352287"
---
# <a name="param-visual-basic"></a><span data-ttu-id="3be95-101">\<参数 > （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="3be95-101">\<param> (Visual Basic)</span></span>
<span data-ttu-id="3be95-102">定义参数名称和说明。</span><span class="sxs-lookup"><span data-stu-id="3be95-102">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3be95-103">语法</span><span class="sxs-lookup"><span data-stu-id="3be95-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a><span data-ttu-id="3be95-104">参数</span><span class="sxs-lookup"><span data-stu-id="3be95-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="3be95-105">方法参数的名称。</span><span class="sxs-lookup"><span data-stu-id="3be95-105">The name of a method parameter.</span></span> <span data-ttu-id="3be95-106">用双引号 (" ") 将名称引起来。</span><span class="sxs-lookup"><span data-stu-id="3be95-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="3be95-107">参数的说明。</span><span class="sxs-lookup"><span data-stu-id="3be95-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3be95-108">备注</span><span class="sxs-lookup"><span data-stu-id="3be95-108">Remarks</span></span>  
 <span data-ttu-id="3be95-109">应在方法声明的注释中使用 `<param>` 标记来描述方法的参数之一。</span><span class="sxs-lookup"><span data-stu-id="3be95-109">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="3be95-110">`<param>` 标记的文本将出现在以下位置：</span><span class="sxs-lookup"><span data-stu-id="3be95-110">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
- <span data-ttu-id="3be95-111">IntelliSense 的参数信息。</span><span class="sxs-lookup"><span data-stu-id="3be95-111">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="3be95-112">有关详细信息，请参阅 [Using IntelliSense](/visualstudio/ide/using-intellisense)。</span><span class="sxs-lookup"><span data-stu-id="3be95-112">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>  
  
- <span data-ttu-id="3be95-113">对象浏览器。</span><span class="sxs-lookup"><span data-stu-id="3be95-113">Object Browser.</span></span> <span data-ttu-id="3be95-114">有关详细信息，请参阅[查看代码的结构](/visualstudio/ide/viewing-the-structure-of-code)。</span><span class="sxs-lookup"><span data-stu-id="3be95-114">For more information, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="3be95-115">使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="3be95-115">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3be95-116">示例</span><span class="sxs-lookup"><span data-stu-id="3be95-116">Example</span></span>  
 <span data-ttu-id="3be95-117">此示例使用 `<param>` 标记来描述 `id` 参数。</span><span class="sxs-lookup"><span data-stu-id="3be95-117">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="3be95-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3be95-118">See also</span></span>

- [<span data-ttu-id="3be95-119">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="3be95-119">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
