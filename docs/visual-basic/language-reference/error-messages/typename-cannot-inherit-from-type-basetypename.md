---
title: "&#39;&lt;typename&gt;&#39; 不能继承自&lt;类型&gt;&#39;&lt;基类型名称&gt;&#39; 因为它将扩展基访问权限&lt;类型&gt;程序集外部"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30910
- bc30910
helpviewer_keywords: BC30910
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d01981d3136968ae2534539b8eccab4c5c535fbc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="39lttypenamegt39-cannot-inherit-from-lttypegt-39ltbasetypenamegt39-because-it-expands-the-access-of-the-base-lttypegt-outside-the-assembly"></a>&#39;&lt;typename&gt;&#39; 不能继承自&lt;类型&gt;&#39;&lt;基类型名称&gt;&#39; 因为它将扩展基访问权限&lt;类型&gt;程序集外部
类或接口继承自的基类或接口，但是具有限制性较弱的访问级别。  
  
 例如，`Public`接口继承自`Friend`接口，或`Protected`类继承自`Private`类。 这会公开基类或接口来访问不在预期级别。  
  
 **错误 ID:** BC30910  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   更改派生的类或接口让至少作为基类或接口的限制性最高的访问级别。  
  
     - 或 -  
  
-   如果你需要的限制性较弱的访问级别，删除`Inherits`语句。 不能从更受限制的基类或接口继承。  
  
## <a name="see-also"></a>另请参阅  
 [Class 语句](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Interface 语句](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Inherits 语句](../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [在 Visual Basic 中的访问级别](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
