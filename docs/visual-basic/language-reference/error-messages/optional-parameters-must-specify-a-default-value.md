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
# <a name="optional-parameters-must-specify-a-default-value"></a><span data-ttu-id="9549e-102">可选参数必须指定默认值</span><span class="sxs-lookup"><span data-stu-id="9549e-102">Optional parameters must specify a default value</span></span>
<span data-ttu-id="9549e-103">可选参数必须不提供任何参数提供的调用过程可以使用的默认值。</span><span class="sxs-lookup"><span data-stu-id="9549e-103">Optional parameters must provide default values that can be used if no parameter is supplied by a calling procedure.</span></span>  
  
 <span data-ttu-id="9549e-104">**错误 ID:** BC30812</span><span class="sxs-lookup"><span data-stu-id="9549e-104">**Error ID:** BC30812</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9549e-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="9549e-105">To correct this error</span></span>  
  
-   <span data-ttu-id="9549e-106">指定可选参数; 默认的值例如：</span><span class="sxs-lookup"><span data-stu-id="9549e-106">Specify default values for optional parameters; for example:</span></span>  
  
    ```  
    Sub Proc1(ByVal X As Integer,   
          Optional ByVal Y As String = "Default Value")  
       MsgBox("Default argument is: " & Y)  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9549e-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="9549e-107">See also</span></span>

- [<span data-ttu-id="9549e-108">Optional</span><span class="sxs-lookup"><span data-stu-id="9549e-108">Optional</span></span>](../../../visual-basic/language-reference/modifiers/optional.md)
