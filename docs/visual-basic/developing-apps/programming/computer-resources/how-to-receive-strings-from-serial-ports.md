---
title: "如何：在 Visual Basic 中从串行端口接收字符串"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- serial ports, retrieving strings
- strings [Visual Basic], retrieving from serial ports
- My.Resources object
ms.assetid: 8371ce2c-e1c7-476b-a86d-9afc2614b6b7
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 500a6c651f6eb991eb9fefef601d0f593a38352f
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-receive-strings-from-serial-ports-in-visual-basic"></a><span data-ttu-id="adbb7-102">如何：在 Visual Basic 中从串行端口接收字符串</span><span class="sxs-lookup"><span data-stu-id="adbb7-102">How to: Receive Strings From Serial Ports in Visual Basic</span></span>
<span data-ttu-id="adbb7-103">本主题介绍在 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 中如何使用 `My.Computer.Ports` 从计算机的串行端口接收字符串。</span><span class="sxs-lookup"><span data-stu-id="adbb7-103">This topic describes how to use `My.Computer.Ports` to receive strings from the computer's serial ports in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
### <a name="to-receive-strings-from-the-serial-port"></a><span data-ttu-id="adbb7-104">从串行端口接收字符串</span><span class="sxs-lookup"><span data-stu-id="adbb7-104">To receive strings from the serial port</span></span>  
  
1.  <span data-ttu-id="adbb7-105">初始化返回字符串。</span><span class="sxs-lookup"><span data-stu-id="adbb7-105">Initialize the return string.</span></span>  
  
     <span data-ttu-id="adbb7-106">[!code-vb[VbVbalrMyComputer#38](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="adbb7-106">[!code-vb[VbVbalrMyComputer#38](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_1.vb)]</span></span>  
  
2.  <span data-ttu-id="adbb7-107">确定应提供字符串的串行端口。</span><span class="sxs-lookup"><span data-stu-id="adbb7-107">Determine which serial port should provide the strings.</span></span> <span data-ttu-id="adbb7-108">此示例假定它是 `COM1`。</span><span class="sxs-lookup"><span data-stu-id="adbb7-108">This example assumes it is `COM1`.</span></span>  
  
3.  <span data-ttu-id="adbb7-109">使用 `My.Computer.Ports.OpenSerialPort` 方法获取对端口的引用。</span><span class="sxs-lookup"><span data-stu-id="adbb7-109">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="adbb7-110">有关详细信息，请参阅<xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>。</span><span class="sxs-lookup"><span data-stu-id="adbb7-110">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
     <span data-ttu-id="adbb7-111">`Try...Catch...Finally` 块允许应用程序在即使会生成异常的情况下也关闭串行端口。</span><span class="sxs-lookup"><span data-stu-id="adbb7-111">The `Try...Catch...Finally` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="adbb7-112">操作串行端口的所有代码都应出现在此块中。</span><span class="sxs-lookup"><span data-stu-id="adbb7-112">All code that manipulates the serial port should appear within this block.</span></span>  
  
     <span data-ttu-id="adbb7-113">[!code-vb[VbVbalrMyComputer#39](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="adbb7-113">[!code-vb[VbVbalrMyComputer#39](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_2.vb)]</span></span>  
  
4.  <span data-ttu-id="adbb7-114">创建 `Do` 循环，用于读取文本行，直到没有更多行可用。</span><span class="sxs-lookup"><span data-stu-id="adbb7-114">Create a `Do` loop for reading lines of text until no more lines are available.</span></span>  
  
     <span data-ttu-id="adbb7-115">[!code-vb[VbVbalrMyComputer#40](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="adbb7-115">[!code-vb[VbVbalrMyComputer#40](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_3.vb)]</span></span>  
  
5.  <span data-ttu-id="adbb7-116">使用 <xref:System.IO.Ports.SerialPort.ReadLine%2A> 方法来从串行端口读取下一个可用的文本行。</span><span class="sxs-lookup"><span data-stu-id="adbb7-116">Use the <xref:System.IO.Ports.SerialPort.ReadLine%2A> method to read the next available line of text from the serial port.</span></span>  
  
     <span data-ttu-id="adbb7-117">[!code-vb[VbVbalrMyComputer#41](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="adbb7-117">[!code-vb[VbVbalrMyComputer#41](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_4.vb)]</span></span>  
  
6.  <span data-ttu-id="adbb7-118">使用 `If` 语句可确定 <xref:System.IO.Ports.SerialPort.ReadLine%2A> 方法是否返回 `Nothing`（这意味着没有更多文本可用）。</span><span class="sxs-lookup"><span data-stu-id="adbb7-118">Use an `If` statement to determine if the <xref:System.IO.Ports.SerialPort.ReadLine%2A> method returns `Nothing` (which means no more text is available).</span></span> <span data-ttu-id="adbb7-119">如果它未返回 `Nothing`，则退出 `Do` 循环。</span><span class="sxs-lookup"><span data-stu-id="adbb7-119">If it does return `Nothing`, exit the `Do` loop.</span></span>  
  
     <span data-ttu-id="adbb7-120">[!code-vb[VbVbalrMyComputer#42](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="adbb7-120">[!code-vb[VbVbalrMyComputer#42](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_5.vb)]</span></span>  
  
7.  <span data-ttu-id="adbb7-121">向 `If` 语句添加 `Else` 块以处理实际读取字符串的情况。</span><span class="sxs-lookup"><span data-stu-id="adbb7-121">Add an `Else` block to the `If` statement to handle the case if the string is actually read.</span></span> <span data-ttu-id="adbb7-122">该块将来自串行端口的字符串追加到返回字符串。</span><span class="sxs-lookup"><span data-stu-id="adbb7-122">The block appends the string from the serial port to the return string.</span></span>  
  
     <span data-ttu-id="adbb7-123">[!code-vb[VbVbalrMyComputer#43](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="adbb7-123">[!code-vb[VbVbalrMyComputer#43](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_6.vb)]</span></span>  
  
8.  <span data-ttu-id="adbb7-124">返回字符串。</span><span class="sxs-lookup"><span data-stu-id="adbb7-124">Return the string.</span></span>  
  
     <span data-ttu-id="adbb7-125">[!code-vb[VbVbalrMyComputer#44](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="adbb7-125">[!code-vb[VbVbalrMyComputer#44](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_7.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="adbb7-126">示例</span><span class="sxs-lookup"><span data-stu-id="adbb7-126">Example</span></span>  
 <span data-ttu-id="adbb7-127">[!code-vb[VbVbalrMyComputer#37](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="adbb7-127">[!code-vb[VbVbalrMyComputer#37](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-receive-strings-from-serial-ports_8.vb)]</span></span>  
  
 <span data-ttu-id="adbb7-128">此代码示例也可作为 IntelliSense 代码片段。</span><span class="sxs-lookup"><span data-stu-id="adbb7-128">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="adbb7-129">它位于代码片段选取器的“连接和网络”中。</span><span class="sxs-lookup"><span data-stu-id="adbb7-129">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="adbb7-130">有关详细信息，请参阅[代码片段](/visualstudio/ide/code-snippets)。</span><span class="sxs-lookup"><span data-stu-id="adbb7-130">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="adbb7-131">编译代码</span><span class="sxs-lookup"><span data-stu-id="adbb7-131">Compiling the Code</span></span>  
 <span data-ttu-id="adbb7-132">本示例假定计算机正在使用 `COM1`。</span><span class="sxs-lookup"><span data-stu-id="adbb7-132">This example assumes the computer is using `COM1`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="adbb7-133">可靠编程</span><span class="sxs-lookup"><span data-stu-id="adbb7-133">Robust Programming</span></span>  
 <span data-ttu-id="adbb7-134">本示例假定计算机正在使用 `COM1`。</span><span class="sxs-lookup"><span data-stu-id="adbb7-134">This example assumes the computer is using `COM1`.</span></span> <span data-ttu-id="adbb7-135">为了获得更大的灵活性，代码应允许用户从可用端口列表中选择所需的串行端口。</span><span class="sxs-lookup"><span data-stu-id="adbb7-135">For more flexibility, the code should allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="adbb7-136">有关详细信息，请参阅[如何：显示可用的串行端口](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)。</span><span class="sxs-lookup"><span data-stu-id="adbb7-136">For more information, see [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="adbb7-137">此示例使用 `Try...Catch...Finally` 块确保应用程序关闭端口以及捕获任何超时异常。</span><span class="sxs-lookup"><span data-stu-id="adbb7-137">This example uses a `Try...Catch...Finally` block to make sure that the application closes the port and to catch any timeout exceptions.</span></span> <span data-ttu-id="adbb7-138">有关详细信息，请参阅 [Try...Catch...Finally 语句](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="adbb7-138">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="adbb7-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="adbb7-139">See Also</span></span>  
 <span data-ttu-id="adbb7-140"><xref:Microsoft.VisualBasic.Devices.Ports></span><span class="sxs-lookup"><span data-stu-id="adbb7-140"><xref:Microsoft.VisualBasic.Devices.Ports></span></span>   
 <span data-ttu-id="adbb7-141"><xref:System.IO.Ports.SerialPort?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="adbb7-141"><xref:System.IO.Ports.SerialPort?displayProperty=fullName></span></span>   
 <span data-ttu-id="adbb7-142">[如何：使用连接到串行端口的调制解调器拨号](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md) </span><span class="sxs-lookup"><span data-stu-id="adbb7-142">[How to: Dial Modems Attached to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md) </span></span>  
 <span data-ttu-id="adbb7-143">[如何：将字符串发送到串行端口](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md) </span><span class="sxs-lookup"><span data-stu-id="adbb7-143">[How to: Send Strings to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md) </span></span>  
 [<span data-ttu-id="adbb7-144">如何：显示可用的串行端口</span><span class="sxs-lookup"><span data-stu-id="adbb7-144">How to: Show Available Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)

