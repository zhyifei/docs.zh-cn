---
title: 如何：编写日志消息 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application.Log object, writing log messags
ms.assetid: 972a3e0c-2996-4623-a7a9-d7ebc4d207f8
ms.openlocfilehash: 8b0d50e70572d849f20f01914d2380a64e4495a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-write-log-messages-visual-basic"></a>如何：编写日志消息 (Visual Basic)
可以使用 `My.Application.Log` 和 `My.Log` 对象来记录有关应用程序的信息。 本示例将演示如何使用 `My.Application.Log.WriteEntry` 方法来记录跟踪信息。  
  
 若要记录异常信息，请使用 `My.Application.Log.WriteException` 方法；请参阅[如何：记录异常](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)。  
  
## <a name="example"></a>示例  
 本示例将使用 `My.Application.Log.WriteEntry` 方法来写出跟踪信息。  
  
 [!code-vb[VbVbalrMyApplicationLog#11](../../../../visual-basic/developing-apps/programming/log-info/codesnippet/VisualBasic/how-to-write-log-messages_1.vb)]  
  
## <a name="net-framework-security"></a>.NET Framework 安全性  
 请确保写入日志的数据不包含敏感信息，如用户密码。 有关详细信息，请参阅[使用应用程序日志](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>  
 <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>  
 <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>  
 [使用应用程序日志](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)  
 [如何：日志异常](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)  
 [演练：确定 My.Application.Log 写入信息的位置](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)  
 [演练：更改 My.Application.Log 写入信息的位置](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)  
 [演练：筛选 My.Application.Log 输出](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)
