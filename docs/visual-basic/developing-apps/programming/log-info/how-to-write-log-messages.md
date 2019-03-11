---
title: 如何：编写日志消息 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.Application.Log object, writing log messages
ms.assetid: 972a3e0c-2996-4623-a7a9-d7ebc4d207f8
ms.openlocfilehash: 007d08917ed5ecae6889d03d820d48e4695c9344
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2019
ms.locfileid: "57676117"
---
# <a name="how-to-write-log-messages-visual-basic"></a><span data-ttu-id="b8096-102">如何：编写日志消息 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8096-102">How to: Write Log Messages (Visual Basic)</span></span>

<span data-ttu-id="b8096-103">可以使用 `My.Application.Log` 和 `My.Log` 对象来记录有关应用程序的信息。</span><span class="sxs-lookup"><span data-stu-id="b8096-103">You can use the `My.Application.Log` and `My.Log` objects to log information about your application.</span></span> <span data-ttu-id="b8096-104">本示例将演示如何使用 `My.Application.Log.WriteEntry` 方法来记录跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="b8096-104">This example shows how to use the `My.Application.Log.WriteEntry` method to log tracing information.</span></span>

<span data-ttu-id="b8096-105">若要记录异常信息，请使用 `My.Application.Log.WriteException` 方法；请参阅[如何：记录异常](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)。</span><span class="sxs-lookup"><span data-stu-id="b8096-105">For logging exception information, use the `My.Application.Log.WriteException` method; see [How to: Log Exceptions](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md).</span></span>

## <a name="example"></a><span data-ttu-id="b8096-106">示例</span><span class="sxs-lookup"><span data-stu-id="b8096-106">Example</span></span>

<span data-ttu-id="b8096-107">本示例将使用 `My.Application.Log.WriteEntry` 方法来写出跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="b8096-107">This example uses the `My.Application.Log.WriteEntry` method to write out the trace information.</span></span>

[!code-vb[VbVbalrMyApplicationLog#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#11)]

## <a name="net-framework-security"></a><span data-ttu-id="b8096-108">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="b8096-108">.NET Framework Security</span></span>

<span data-ttu-id="b8096-109">请确保写入日志的数据不包含敏感信息，如用户密码。</span><span class="sxs-lookup"><span data-stu-id="b8096-109">Make sure the data you write to the log does not include sensitive information such as user passwords.</span></span> <span data-ttu-id="b8096-110">有关详细信息，请参阅[使用应用程序日志](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)。</span><span class="sxs-lookup"><span data-stu-id="b8096-110">For more information, see [Working with Application Logs](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b8096-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="b8096-111">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteEntry%2A>
- <xref:Microsoft.VisualBasic.Logging.Log.WriteException%2A>
- [<span data-ttu-id="b8096-112">使用应用程序日志</span><span class="sxs-lookup"><span data-stu-id="b8096-112">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [<span data-ttu-id="b8096-113">如何：日志异常</span><span class="sxs-lookup"><span data-stu-id="b8096-113">How to: Log Exceptions</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)
- [<span data-ttu-id="b8096-114">演练：确定 My.Application.Log 在哪里写入信息</span><span class="sxs-lookup"><span data-stu-id="b8096-114">Walkthrough: Determining Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-determining-where-my-application-log-writes-information.md)
- [<span data-ttu-id="b8096-115">演练：更改 My.Application.Log 在哪里写入信息</span><span class="sxs-lookup"><span data-stu-id="b8096-115">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
- [<span data-ttu-id="b8096-116">演练：筛选 My.Application.Log 输出</span><span class="sxs-lookup"><span data-stu-id="b8096-116">Walkthrough: Filtering My.Application.Log Output</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-filtering-my-application-log-output.md)
