---
title: 指令 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: 38d54feae5cf7bf41a825d1f6000811e2b56f319
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2018
ms.locfileid: "43736602"
---
# <a name="directives-visual-basic"></a>指令 (Visual Basic)
本节中的主题记录 Visual Basic 源代码编译器指令。  
  
## <a name="in-this-section"></a>本节内容  
 [#Const 指令](../../../visual-basic/language-reference/directives/const-directive.md)-定义编译器常量  
  
 [#ExternalSource 指令](../../../visual-basic/language-reference/directives/externalsource-directive.md)-指示源行和源的外部文本之间的映射  
  
 [#If......#Else 指令](../../../visual-basic/language-reference/directives/if-then-else-directives.md)-编译选定的代码块  
  
 [#Region 指令](../../../visual-basic/language-reference/directives/region-directive.md)： 折叠并隐藏 Visual Studio 编辑器中的代码段  
  
 **#Disable、 #Enable** ： 禁用和启用地区代码的特定警告。  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
```  
  
 还可以禁用和启用以逗号分隔的警告代码列表。  
  
## <a name="related-sections"></a>相关章节  
 [Visual Basic 语言参考](../../../visual-basic/language-reference/index.md)  
  
 [Visual Basic](../../../visual-basic/index.md)
