---
title: 可选参数必须指定默认值
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: 01c0abb366e8605a9b153333e645fc3276b6bd16
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821720"
---
# <a name="optional-parameters-must-specify-a-default-value"></a>可选参数必须指定默认值
可选参数必须不提供任何参数提供的调用过程可以使用的默认值。  
  
 **错误 ID:** BC30812  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
-   指定可选参数; 默认的值例如：  
  
    ```  
    Sub Proc1(ByVal X As Integer,   
          Optional ByVal Y As String = "Default Value")  
       MsgBox("Default argument is: " & Y)  
    End Sub  
    ```  
  
## <a name="see-also"></a>请参阅

- [Optional](../../../visual-basic/language-reference/modifiers/optional.md)
