---
title: '#Region 指令'
ms.date: 07/20/2015
f1_keywords:
- vb.Region
- vb.#Region
helpviewer_keywords:
- Visual Basic compiler, compiler directives
- '#region directive'
- region directive (#region)
- '#Region keyword [Visual Basic]'
ms.assetid: 90a6a104-3cbf-47d0-bdc4-b585d0921b87
ms.openlocfilehash: d25871140ef0674c013fc70d1306b2b4d0858556
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="region-directive"></a><span data-ttu-id="629d4-102">#Region 指令</span><span class="sxs-lookup"><span data-stu-id="629d4-102">#Region Directive</span></span>
<span data-ttu-id="629d4-103">折叠并隐藏 Visual Basic 文件中的代码段。</span><span class="sxs-lookup"><span data-stu-id="629d4-103">Collapses and hides sections of code in Visual Basic files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="629d4-104">语法</span><span class="sxs-lookup"><span data-stu-id="629d4-104">Syntax</span></span>  

```vb
#Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a><span data-ttu-id="629d4-105">部件</span><span class="sxs-lookup"><span data-stu-id="629d4-105">Parts</span></span>  
  
|<span data-ttu-id="629d4-106">术语</span><span class="sxs-lookup"><span data-stu-id="629d4-106">Term</span></span>|<span data-ttu-id="629d4-107">定义</span><span class="sxs-lookup"><span data-stu-id="629d4-107">Definition</span></span>|  
|---|---|  
|`identifier_string`|<span data-ttu-id="629d4-108">必须的。</span><span class="sxs-lookup"><span data-stu-id="629d4-108">Required.</span></span> <span data-ttu-id="629d4-109">当区域处于折叠状态时充当区域标题的字符串。</span><span class="sxs-lookup"><span data-stu-id="629d4-109">String that acts as the title of a region when it is collapsed.</span></span> <span data-ttu-id="629d4-110">默认情况下，区域处于折叠状态。</span><span class="sxs-lookup"><span data-stu-id="629d4-110">Regions are collapsed by default.</span></span>|  
|`#End Region`|<span data-ttu-id="629d4-111">终止 `#Region` 块。</span><span class="sxs-lookup"><span data-stu-id="629d4-111">Terminates the `#Region` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="629d4-112">备注</span><span class="sxs-lookup"><span data-stu-id="629d4-112">Remarks</span></span>  
 <span data-ttu-id="629d4-113">使用 `#Region` 指令指定使用 Visual Studio 代码编辑器的大纲显示功能时要展开或折叠的代码块。</span><span class="sxs-lookup"><span data-stu-id="629d4-113">Use the `#Region` directive to specify a block of code to expand or collapse when using the outlining feature of the Visual Studio Code Editor.</span></span> <span data-ttu-id="629d4-114">你可以将放置，或*嵌套*，在将类似区域组合在一起其他区域。</span><span class="sxs-lookup"><span data-stu-id="629d4-114">You can place, or *nest*, regions within other regions to group similar regions together.</span></span>  
  
## <a name="example"></a><span data-ttu-id="629d4-115">示例</span><span class="sxs-lookup"><span data-stu-id="629d4-115">Example</span></span>  
 <span data-ttu-id="629d4-116">此示例使用 `#Region` 指令。</span><span class="sxs-lookup"><span data-stu-id="629d4-116">This example uses the `#Region` directive.</span></span>  
  
 [!code-vb[VbVbalrConditionalComp#4](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="629d4-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="629d4-117">See Also</span></span>  
 [<span data-ttu-id="629d4-118">#If...Then...#Else 指令</span><span class="sxs-lookup"><span data-stu-id="629d4-118">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [<span data-ttu-id="629d4-119">大纲显示</span><span class="sxs-lookup"><span data-stu-id="629d4-119">Outlining</span></span>](/visualstudio/ide/outlining)  
 [<span data-ttu-id="629d4-120">如何：折叠和隐藏代码节</span><span class="sxs-lookup"><span data-stu-id="629d4-120">How to: Collapse and Hide Sections of Code</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)
