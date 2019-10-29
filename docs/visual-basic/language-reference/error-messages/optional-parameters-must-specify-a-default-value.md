---
title: 可选参数必须指定默认值
ms.date: 07/20/2015
f1_keywords:
- vbc30812
- bc30812
helpviewer_keywords:
- BC30812
ms.assetid: 5091a250-be66-413b-98a3-2a9974c4d600
ms.openlocfilehash: eb782b2fa1fb73c7407b57a0942e5eebb30474ff
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040927"
---
# <a name="optional-parameters-must-specify-a-default-value"></a><span data-ttu-id="8a8fa-102">可选参数必须指定默认值</span><span class="sxs-lookup"><span data-stu-id="8a8fa-102">Optional parameters must specify a default value</span></span>

<span data-ttu-id="8a8fa-103">可选参数必须提供默认值，如果调用过程未提供任何参数，则可以使用这些默认值。</span><span class="sxs-lookup"><span data-stu-id="8a8fa-103">Optional parameters must provide default values that can be used if no parameter is supplied by a calling procedure.</span></span>

<span data-ttu-id="8a8fa-104">**错误 ID：** BC30812</span><span class="sxs-lookup"><span data-stu-id="8a8fa-104">**Error ID:** BC30812</span></span>

## <a name="example"></a><span data-ttu-id="8a8fa-105">示例</span><span class="sxs-lookup"><span data-stu-id="8a8fa-105">Example</span></span>

<span data-ttu-id="8a8fa-106">下面的示例生成 BC30812：</span><span class="sxs-lookup"><span data-stu-id="8a8fa-106">The following example generates BC30812:</span></span>

```vb
Sub Proc1(x As Integer, Optional y As String)
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="to-correct-this-error"></a><span data-ttu-id="8a8fa-107">更正此错误</span><span class="sxs-lookup"><span data-stu-id="8a8fa-107">To correct this error</span></span>

<span data-ttu-id="8a8fa-108">指定可选参数的默认值：</span><span class="sxs-lookup"><span data-stu-id="8a8fa-108">Specify default values for optional parameters:</span></span>

```vb
Sub Proc1(x As Integer, Optional y As String = "Default Value")
    Console.WriteLine("Default argument is: " & y)
End Sub
```

## <a name="see-also"></a><span data-ttu-id="8a8fa-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a8fa-109">See also</span></span>

- [<span data-ttu-id="8a8fa-110">Optional</span><span class="sxs-lookup"><span data-stu-id="8a8fa-110">Optional</span></span>](../modifiers/optional.md)
