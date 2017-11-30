---
title: "#<a name=\"region-directive\"></a>Region 指令"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Region
- vb.#Region
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword [Visual Basic]'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fb308da6ad0ca6243f14e0d825ed7eb005d622bc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="region-directive"></a><span data-ttu-id="df779-102">#Region 指令</span><span class="sxs-lookup"><span data-stu-id="df779-102">#Region Directive</span></span>
<span data-ttu-id="df779-103">折叠并隐藏 Visual Basic 文件中的代码段。</span><span class="sxs-lookup"><span data-stu-id="df779-103">Collapses and hides sections of code in Visual Basic files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df779-104">语法</span><span class="sxs-lookup"><span data-stu-id="df779-104">Syntax</span></span>  
  
```  
      #Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a><span data-ttu-id="df779-105">部件</span><span class="sxs-lookup"><span data-stu-id="df779-105">Parts</span></span>  
  
|<span data-ttu-id="df779-106">术语</span><span class="sxs-lookup"><span data-stu-id="df779-106">Term</span></span>|<span data-ttu-id="df779-107">定义</span><span class="sxs-lookup"><span data-stu-id="df779-107">Definition</span></span>|  
|---|---|  
|`identifier_string`|<span data-ttu-id="df779-108">必需。</span><span class="sxs-lookup"><span data-stu-id="df779-108">Required.</span></span> <span data-ttu-id="df779-109">当区域处于折叠状态时充当区域标题的字符串。</span><span class="sxs-lookup"><span data-stu-id="df779-109">String that acts as the title of a region when it is collapsed.</span></span> <span data-ttu-id="df779-110">默认情况下，区域处于折叠状态。</span><span class="sxs-lookup"><span data-stu-id="df779-110">Regions are collapsed by default.</span></span>|  
|`#End Region`|<span data-ttu-id="df779-111">终止 `#Region` 块。</span><span class="sxs-lookup"><span data-stu-id="df779-111">Terminates the `#Region` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="df779-112">备注</span><span class="sxs-lookup"><span data-stu-id="df779-112">Remarks</span></span>  
 <span data-ttu-id="df779-113">使用 `#Region` 指令指定使用 Visual Studio 代码编辑器的大纲显示功能时要展开或折叠的代码块。</span><span class="sxs-lookup"><span data-stu-id="df779-113">Use the `#Region` directive to specify a block of code to expand or collapse when using the outlining feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="df779-114">你可以将放置，或*嵌套*，在将类似区域组合在一起其他区域。</span><span class="sxs-lookup"><span data-stu-id="df779-114">You can place, or *nest*, regions within other regions to group similar regions together.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df779-115">示例</span><span class="sxs-lookup"><span data-stu-id="df779-115">Example</span></span>  
 <span data-ttu-id="df779-116">此示例使用 `#Region` 指令。</span><span class="sxs-lookup"><span data-stu-id="df779-116">This example uses the `#Region` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#4](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="df779-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="df779-117">See Also</span></span>  
 [<span data-ttu-id="df779-118">#If...Then...#Else 指令</span><span class="sxs-lookup"><span data-stu-id="df779-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="df779-119">大纲显示</span><span class="sxs-lookup"><span data-stu-id="df779-119">Outlining</span></span>](/visualstudio/ide/outlining)  
 [<span data-ttu-id="df779-120">如何：折叠和隐藏代码节</span><span class="sxs-lookup"><span data-stu-id="df779-120">How to: Collapse and Hide Sections of Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)
