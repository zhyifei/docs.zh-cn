---
title: "指令 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8219f17f1b8093b4d02b370c7b008101923b1873
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="directives-visual-basic"></a>指令 (Visual Basic)
本节中的主题记录 Visual Basic 源代码编译器指令。  
  
## <a name="in-this-section"></a>本节内容  
 [#Const 指令](../../../visual-basic/language-reference/directives/const-directive.md)-定义编译器常量  
  
 [#ExternalSource 指令](../../../visual-basic/language-reference/directives/externalsource-directive.md)-指示源行和源的外部文本之间的映射  
  
 [#If......#Else 指令](../../../visual-basic/language-reference/directives/if-then-else-directives.md)-编译选定的代码块  
  
 [#Region 指令](../../../visual-basic/language-reference/directives/region-directive.md)： 折叠并隐藏 Visual Studio 编辑器中的代码段  
  
 **#Disable disable，#Enable** ： 禁用和启用地区代码的特定警告。  
  
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
