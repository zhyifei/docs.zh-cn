---
title: "#Region 指令 |Microsoft 文档"
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Region
- vb.#Region
dev_langs:
- VB
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 86b8e9ce99a8c12e290f5efdc5a5c4da57f350d9
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="region-directive"></a>#<span data-ttu-id="a8895-102">Region 指令</span><span class="sxs-lookup"><span data-stu-id="a8895-102">Region Directive</span></span>
<span data-ttu-id="a8895-103">折叠并隐藏 Visual Basic 文件中的代码段。</span><span class="sxs-lookup"><span data-stu-id="a8895-103">Collapses and hides sections of code in Visual Basic files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8895-104">语法</span><span class="sxs-lookup"><span data-stu-id="a8895-104">Syntax</span></span>  
  
```  
  
      #Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a><span data-ttu-id="a8895-105">部件</span><span class="sxs-lookup"><span data-stu-id="a8895-105">Parts</span></span>  
  
|<span data-ttu-id="a8895-106">术语</span><span class="sxs-lookup"><span data-stu-id="a8895-106">Term</span></span>|<span data-ttu-id="a8895-107">定义</span><span class="sxs-lookup"><span data-stu-id="a8895-107">Definition</span></span>|  
|---|---|  
|`identifier_string`|<span data-ttu-id="a8895-108">必需。</span><span class="sxs-lookup"><span data-stu-id="a8895-108">Required.</span></span> <span data-ttu-id="a8895-109">当区域处于折叠状态时充当区域标题的字符串。</span><span class="sxs-lookup"><span data-stu-id="a8895-109">String that acts as the title of a region when it is collapsed.</span></span> <span data-ttu-id="a8895-110">默认情况下，区域处于折叠状态。</span><span class="sxs-lookup"><span data-stu-id="a8895-110">Regions are collapsed by default.</span></span>|  
|`#End Region`|<span data-ttu-id="a8895-111">终止 `#Region` 块。</span><span class="sxs-lookup"><span data-stu-id="a8895-111">Terminates the `#Region` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a8895-112">备注</span><span class="sxs-lookup"><span data-stu-id="a8895-112">Remarks</span></span>  
 <span data-ttu-id="a8895-113">使用 `#Region` 指令指定使用 Visual Studio 代码编辑器的大纲显示功能时要展开或折叠的代码块。</span><span class="sxs-lookup"><span data-stu-id="a8895-113">Use the `#Region` directive to specify a block of code to expand or collapse when using the outlining feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="a8895-114">您可以放置或*嵌套*，在其他区域分为一组类似的区域。</span><span class="sxs-lookup"><span data-stu-id="a8895-114">You can place, or *nest*, regions within other regions to group similar regions together.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8895-115">示例</span><span class="sxs-lookup"><span data-stu-id="a8895-115">Example</span></span>  
 <span data-ttu-id="a8895-116">此示例使用 `#Region` 指令。</span><span class="sxs-lookup"><span data-stu-id="a8895-116">This example uses the `#Region` directive.</span></span>  
  
 <span data-ttu-id="a8895-117">[!code-vb[VbVbalrConditionalComp #&4;](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="a8895-117">[!code-vb[VbVbalrConditionalComp#4](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8895-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a8895-118">See Also</span></span>  
 <span data-ttu-id="a8895-119">[#If...Then...#Else 指令](../../../visual-basic/language-reference/directives/if-then-else-directives.md) </span><span class="sxs-lookup"><span data-stu-id="a8895-119">[#If...Then...#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) </span></span>  
<span data-ttu-id="a8895-120"> [大纲显示](https://docs.microsoft.com/visualstudio/ide/outlining) </span><span class="sxs-lookup"><span data-stu-id="a8895-120"> [Outlining](https://docs.microsoft.com/visualstudio/ide/outlining) </span></span>  
<span data-ttu-id="a8895-121"> [如何：折叠和隐藏代码节](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)</span><span class="sxs-lookup"><span data-stu-id="a8895-121"> [How to: Collapse and Hide Sections of Code](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)</span></span>
