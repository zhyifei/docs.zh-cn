---
title: "&lt;type1&gt;&#39;&lt;typename&gt;&#39; 必须实现 &#39;&lt;methodname&gt;&#39; 对于接口 &#39;&lt;interfacename&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30149
- bc30149
helpviewer_keywords: BC30149
ms.assetid: 29d1b7f4-dca7-478c-bbe7-c657f342c183
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e803ec7d0054f2fa1b9ed2a731fd30c9c3060468
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="lttype1gt39lttypenamegt39-must-implement-39ltmethodnamegt39-for-interface-39ltinterfacenamegt39"></a>&lt;type1&gt;&#39;&lt;typename&gt;&#39; 必须实现 &#39;&lt;methodname&gt;&#39; 对于接口 &#39;&lt;interfacename&gt;&#39;
类或结构实现接口声明，但不实现由接口定义的过程。 必须实现该接口的每个成员。  
  
 **错误 ID:** BC30149  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  声明具有相同的名称和签名在接口中定义的过程。 请务必包括至少`End Function`或`End Sub`语句。  
  
2.  添加`Implements`子句的末尾`Function`或`Sub`语句。 例如:   
  
    ```  
    Public Sub DoSomething() Implements IBaseInterface.DoSomething  
    ```  
  
## <a name="see-also"></a>另请参阅  
 [Implements 语句](../../../visual-basic/language-reference/statements/implements-statement.md)  
 [接口](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
