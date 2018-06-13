---
title: 可选参数必须指定默认值
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: 6788a7908489591e266af6d141006f2aa2d0e6f1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593911"
---
# <a name="optional-parameters-must-specify-a-default-value"></a><span data-ttu-id="0e769-102">可选参数必须指定默认值</span><span class="sxs-lookup"><span data-stu-id="0e769-102">Optional parameters must specify a default value</span></span>
<span data-ttu-id="0e769-103">可选参数必须不提供在调用过程提供任何参数，则可以使用的默认值。</span><span class="sxs-lookup"><span data-stu-id="0e769-103">Optional parameters must provide default values that can be used if no parameter is supplied by a calling procedure.</span></span>  
  
 <span data-ttu-id="0e769-104">**错误 ID:** BC30812</span><span class="sxs-lookup"><span data-stu-id="0e769-104">**Error ID:** BC30812</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0e769-105">更正此错误</span><span class="sxs-lookup"><span data-stu-id="0e769-105">To correct this error</span></span>  
  
-   <span data-ttu-id="0e769-106">指定默认值为可选参数;例如：</span><span class="sxs-lookup"><span data-stu-id="0e769-106">Specify default values for optional parameters; for example:</span></span>  
  
    ```  
    Sub Proc1(ByVal X As Integer,   
          Optional ByVal Y As String = "Default Value")  
       MsgBox("Default argument is: " & Y)  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0e769-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e769-107">See Also</span></span>  
 [<span data-ttu-id="0e769-108">Optional</span><span class="sxs-lookup"><span data-stu-id="0e769-108">Optional</span></span>](../../../visual-basic/language-reference/modifiers/optional.md)
