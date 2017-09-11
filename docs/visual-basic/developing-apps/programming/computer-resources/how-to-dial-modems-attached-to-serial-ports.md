---
title: "如何：在 Visual Basic 中使用连接到串行端口的调制解调器拨号"
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
- modems, dialing
- serial ports, dialing
- My.Computer.Ports object
ms.assetid: 3834db40-f431-45f1-b671-dc91787164b6
caps.latest.revision: 19
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
ms.openlocfilehash: 0daaf35cdebac3d69ddc536124d4c86b96955b11
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-dial-modems-attached-to-serial-ports-in-visual-basic"></a><span data-ttu-id="ad5c3-102">如何：在 Visual Basic 中使用连接到串行端口的调制解调器拨号</span><span class="sxs-lookup"><span data-stu-id="ad5c3-102">How to: Dial Modems Attached to Serial Ports in Visual Basic</span></span>
<span data-ttu-id="ad5c3-103">本主题介绍如何在 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 中使用 `My.Computer.Ports` 进行调制解调器拨号。</span><span class="sxs-lookup"><span data-stu-id="ad5c3-103">This topic describes how to use `My.Computer.Ports` to dial a modem in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span>  
  
 <span data-ttu-id="ad5c3-104">通常，调制解调器连接到计算机的某个串行端口。</span><span class="sxs-lookup"><span data-stu-id="ad5c3-104">Typically, the modem is connected to one of the serial ports on the computer.</span></span> <span data-ttu-id="ad5c3-105">若要使应用程序与调制解调器通信，必须将命令发送到相应的串行端口。</span><span class="sxs-lookup"><span data-stu-id="ad5c3-105">For your application to communicate with the modem, it must send commands to the appropriate serial port.</span></span>  
  
### <a name="to-dial-a-modem"></a><span data-ttu-id="ad5c3-106">调制解调器拨号</span><span class="sxs-lookup"><span data-stu-id="ad5c3-106">To dial a modem</span></span>  
  
1.  <span data-ttu-id="ad5c3-107">确定调制解调器连接到的串行端口。</span><span class="sxs-lookup"><span data-stu-id="ad5c3-107">Determine which serial port the modem is connected to.</span></span> <span data-ttu-id="ad5c3-108">此示例假定调制解调器在 COM1 上。</span><span class="sxs-lookup"><span data-stu-id="ad5c3-108">This example assumes the modem is on COM1.</span></span>  
  
2.  <span data-ttu-id="ad5c3-109">使用 `My.Computer.Ports.OpenSerialPort` 方法获取对端口的引用。</span><span class="sxs-lookup"><span data-stu-id="ad5c3-109">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="ad5c3-110">有关详细信息，请参阅<xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>。</span><span class="sxs-lookup"><span data-stu-id="ad5c3-110">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
     <span data-ttu-id="ad5c3-111">`Using` 块允许应用程序在即使会生成异常的情况下也关闭串行端口。</span><span class="sxs-lookup"><span data-stu-id="ad5c3-111">The `Using` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="ad5c3-112">操作串行端口的所有代码都应出现在此块中，或者出现在 `Try...Catch...Finally` 块中。</span><span class="sxs-lookup"><span data-stu-id="ad5c3-112">All code that manipulates the serial port should appear within this block, or within a `Try...Catch...Finally` block.</span></span>  
  
     <span data-ttu-id="ad5c3-113">[!code-vb[VbVbalrMyComputer#28](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="ad5c3-113">[!code-vb[VbVbalrMyComputer#28](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_1.vb)]</span></span>  
  
3.  <span data-ttu-id="ad5c3-114">设置 `DtrEnable` 属性，指示计算机已准备好接受从调制解调器传入的传输。</span><span class="sxs-lookup"><span data-stu-id="ad5c3-114">Set the `DtrEnable` property to indicate that the computer is ready to accept an incoming transmission from the modem.</span></span>  
  
     <span data-ttu-id="ad5c3-115">[!code-vb[VbVbalrMyComputer#29](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="ad5c3-115">[!code-vb[VbVbalrMyComputer#29](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_2.vb)]</span></span>  
  
4.  <span data-ttu-id="ad5c3-116">通过 <xref:System.IO.Ports.SerialPort.Write%2A> 方法将拨号命令和电话号码从串行端口发送到调制解调器。</span><span class="sxs-lookup"><span data-stu-id="ad5c3-116">Send the dial command and the phone number to the modem through the serial port by means of the <xref:System.IO.Ports.SerialPort.Write%2A> method.</span></span>  
  
     <span data-ttu-id="ad5c3-117">[!code-vb[VbVbalrMyComputer#30](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="ad5c3-117">[!code-vb[VbVbalrMyComputer#30](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_3.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="ad5c3-118">示例</span><span class="sxs-lookup"><span data-stu-id="ad5c3-118">Example</span></span>  
 <span data-ttu-id="ad5c3-119">[!code-vb[VbVbalrMyComputer#27](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="ad5c3-119">[!code-vb[VbVbalrMyComputer#27](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-dial-modems-attached-to-serial-ports_4.vb)]</span></span>  
  
 <span data-ttu-id="ad5c3-120">此代码示例也可作为 IntelliSense 代码片段。</span><span class="sxs-lookup"><span data-stu-id="ad5c3-120">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="ad5c3-121">它位于代码片段选取器的“连接和网络”中。</span><span class="sxs-lookup"><span data-stu-id="ad5c3-121">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="ad5c3-122">有关详细信息，请参阅[代码片段](/visualstudio/ide/code-snippets)。</span><span class="sxs-lookup"><span data-stu-id="ad5c3-122">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ad5c3-123">编译代码</span><span class="sxs-lookup"><span data-stu-id="ad5c3-123">Compiling the Code</span></span>  
 <span data-ttu-id="ad5c3-124">该示例需要引用 <xref:System?displayProperty=fullName> 命名空间。</span><span class="sxs-lookup"><span data-stu-id="ad5c3-124">This example requires a reference to the <xref:System?displayProperty=fullName> namespace.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ad5c3-125">可靠编程</span><span class="sxs-lookup"><span data-stu-id="ad5c3-125">Robust Programming</span></span>  
 <span data-ttu-id="ad5c3-126">此示例假定调制解调器已连接 COM1。</span><span class="sxs-lookup"><span data-stu-id="ad5c3-126">This example assumes the modem is connected to COM1.</span></span> <span data-ttu-id="ad5c3-127">建议使代码允许用户从可用端口列表中选择所需串行端口。</span><span class="sxs-lookup"><span data-stu-id="ad5c3-127">We recommend that your code allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="ad5c3-128">有关详细信息，请参阅[如何：显示可用的串行端口](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)。</span><span class="sxs-lookup"><span data-stu-id="ad5c3-128">For more information, see [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="ad5c3-129">本示例使用 `Using` 块来确保应用程序在即使会引发异常的情况下也关闭端口。</span><span class="sxs-lookup"><span data-stu-id="ad5c3-129">This example uses a `Using` block to make sure that the application closes the port even if it throws an exception.</span></span> <span data-ttu-id="ad5c3-130">有关详细信息，请参阅 [Using 语句](../../../../visual-basic/language-reference/statements/using-statement.md)。</span><span class="sxs-lookup"><span data-stu-id="ad5c3-130">For more information, see [Using Statement](../../../../visual-basic/language-reference/statements/using-statement.md).</span></span>  
  
 <span data-ttu-id="ad5c3-131">在本例中，应用程序拨打调制解调器后断开了串行端口。</span><span class="sxs-lookup"><span data-stu-id="ad5c3-131">In this example, the application disconnects the serial port after it dials the modem.</span></span> <span data-ttu-id="ad5c3-132">实际上，需要将数据传入和传出调制解调器。</span><span class="sxs-lookup"><span data-stu-id="ad5c3-132">Realistically, you will want to transfer data to and from the modem.</span></span> <span data-ttu-id="ad5c3-133">有关详细信息，请参阅[如何：从串行端口接收字符串](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md)。</span><span class="sxs-lookup"><span data-stu-id="ad5c3-133">For more information, see [How to: Receive Strings From Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad5c3-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ad5c3-134">See Also</span></span>  
 <span data-ttu-id="ad5c3-135"><xref:Microsoft.VisualBasic.Devices.Ports></span><span class="sxs-lookup"><span data-stu-id="ad5c3-135"><xref:Microsoft.VisualBasic.Devices.Ports></span></span>   
 <span data-ttu-id="ad5c3-136"><xref:System.IO.Ports.SerialPort?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="ad5c3-136"><xref:System.IO.Ports.SerialPort?displayProperty=fullName></span></span>   
 <span data-ttu-id="ad5c3-137">[如何：将字符串发送到串行端口](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md) </span><span class="sxs-lookup"><span data-stu-id="ad5c3-137">[How to: Send Strings to Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md) </span></span>  
 <span data-ttu-id="ad5c3-138">[如何：从串行端口接收字符串](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md) </span><span class="sxs-lookup"><span data-stu-id="ad5c3-138">[How to: Receive Strings From Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-receive-strings-from-serial-ports.md) </span></span>  
 [<span data-ttu-id="ad5c3-139">如何：显示可用的串行端口</span><span class="sxs-lookup"><span data-stu-id="ad5c3-139">How to: Show Available Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)

