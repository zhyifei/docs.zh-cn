---
title: "由于内部错误，无法获取完整的操作系统名"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrDiagnosticInfo_FullOSName
ms.assetid: f69da02b-eb9a-4284-bb9e-3025517ae6c1
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c67d47126718c3d90d853add61b7d06aaf84fc70
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/21/2017
---
# <a name="could-not-obtain-full-operation-system-name-due-to-internal-error"></a>由于内部错误，无法获取完整的操作系统名
由于内部错误，无法获取完整的操作系统名。 这可能由当前计算机上不存在 WMI 导致。  
  
 对 `My.Computer.Info.OSFullName` 属性的调用失败。 此失败的可能原因是当前计算机上是否未安装 Windows Management Instrumentation (WMI)。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  将调用周围的 `Try...Catch` 块添加到 `My.Computer.Info.OSFullName` 属性。  
  
2.  有关 WMI 和如何安装它的详细信息，请转到和"Windows Management Instrumentation Core"搜索。  
  
## <a name="see-also"></a>请参阅  
 [My.Computer.Info.OSFullName](xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName)  
 [异常和 Visual Basic 中的错误处理](http://msdn.microsoft.com/en-us/3e351e73-cf23-40ab-8b60-05794160529e)  
 [Try...Catch...Finally 语句](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
