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
# <a name="region-directive"></a>#Region 指令
折叠并隐藏 Visual Basic 文件中的代码段。  
  
## <a name="syntax"></a>语法  
  
```  
      #Region "identifier_string"  
#End Region  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`identifier_string`|必需。 当区域处于折叠状态时充当区域标题的字符串。 默认情况下，区域处于折叠状态。|  
|`#End Region`|终止 `#Region` 块。|  
  
## <a name="remarks"></a>备注  
 使用 `#Region` 指令指定使用 Visual Studio 代码编辑器的大纲显示功能时要展开或折叠的代码块。 你可以将放置，或*嵌套*，在将类似区域组合在一起其他区域。  
  
## <a name="example"></a>示例  
 此示例使用 `#Region` 指令。  
  
 [!code-vb[VbVbalrConditionalComp#4](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/region-directive_1.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [#If...Then...#Else 指令](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [大纲显示](/visualstudio/ide/outlining)  
 [如何：折叠和隐藏代码节](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)
