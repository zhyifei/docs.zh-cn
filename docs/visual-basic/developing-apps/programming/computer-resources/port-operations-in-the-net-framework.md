---
title: 使用 Visual Basic 在 .NET Framework 中执行的端口操作
ms.date: 07/20/2015
helpviewer_keywords:
- ports, Visual Basic
ms.assetid: 1eba223b-7bd3-401a-b097-982bce96df1b
ms.openlocfilehash: 66b3729081540e8dede42556c58e44cd55b62666
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="port-operations-in-the-net-framework-with-visual-basic"></a><span data-ttu-id="64705-102">使用 Visual Basic 在 .NET Framework 中执行的端口操作</span><span class="sxs-lookup"><span data-stu-id="64705-102">Port Operations in the .NET Framework with Visual Basic</span></span>
<span data-ttu-id="64705-103">可以通过 <xref:System.IO.Ports?displayProperty=nameWithType> 命名空间中的 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 类访问计算机的串行端口。</span><span class="sxs-lookup"><span data-stu-id="64705-103">You can access your computer's serial ports through the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classes in the <xref:System.IO.Ports?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="64705-104">最重要的类 <xref:System.IO.Ports.SerialPort> 为同步和事件驱动 I/O 提供框架，提供对插针和中断状态的访问，以及对串行驱动程序属性的访问。</span><span class="sxs-lookup"><span data-stu-id="64705-104">The most important class, <xref:System.IO.Ports.SerialPort>, provides a framework for synchronous and event-driven I/O, access to pin and break states, and access to serial driver properties.</span></span> <span data-ttu-id="64705-105">它可以包装在可通过 <xref:System.IO.Ports.SerialPort.BaseStream> 属性访问的 <xref:System.IO.Stream> 对象中。</span><span class="sxs-lookup"><span data-stu-id="64705-105">It can be wrapped in a <xref:System.IO.Stream> object, accessible through the <xref:System.IO.Ports.SerialPort.BaseStream> property.</span></span> <span data-ttu-id="64705-106">将 <xref:System.IO.Ports.SerialPort> 包装在 <xref:System.IO.Stream> 对象中，以便允许使用流的类访问串行端口。</span><span class="sxs-lookup"><span data-stu-id="64705-106">Wrapping <xref:System.IO.Ports.SerialPort> in a <xref:System.IO.Stream> object allows the serial port to be accessed by classes that use streams.</span></span> <span data-ttu-id="64705-107">该命名空间包含可以简化对串行端口的控制的枚举。</span><span class="sxs-lookup"><span data-stu-id="64705-107">The namespace includes enumerations that simplify the control of serial ports.</span></span>  
  
 <span data-ttu-id="64705-108">创建 <xref:System.IO.Ports.SerialPort> 对象的最简单的方法是通过 <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="64705-108">The simplest way to create a <xref:System.IO.Ports.SerialPort> object is through the <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A> method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64705-109">不能使用 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 类直接访问其他类型的端口，例如并行端口、USB 端口等。</span><span class="sxs-lookup"><span data-stu-id="64705-109">You cannot use [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] classes to directly access other types of ports, such as parallel ports, USB ports, and so on.</span></span>  
  
## <a name="enumerations"></a><span data-ttu-id="64705-110">枚举</span><span class="sxs-lookup"><span data-stu-id="64705-110">Enumerations</span></span>  
 <span data-ttu-id="64705-111">此表列出并描述了用于访问串行端口的主要枚举：</span><span class="sxs-lookup"><span data-stu-id="64705-111">This table lists and describes the main enumerations used for accessing a serial port:</span></span>  
  
|<span data-ttu-id="64705-112">枚举</span><span class="sxs-lookup"><span data-stu-id="64705-112">Enumeration</span></span>|<span data-ttu-id="64705-113">描述</span><span class="sxs-lookup"><span data-stu-id="64705-113">Description</span></span>|  
|---|---|   
|<xref:System.IO.Ports.Handshake>|<span data-ttu-id="64705-114">指定在为 <xref:System.IO.Ports.SerialPort> 对象建立串行端口通信时使用的控制协议。</span><span class="sxs-lookup"><span data-stu-id="64705-114">Specifies the control protocol used in establishing a serial port communication for a <xref:System.IO.Ports.SerialPort> object.</span></span>|  
|<xref:System.IO.Ports.Parity>|<span data-ttu-id="64705-115">指定 <xref:System.IO.Ports.SerialPort> 对象的奇偶校验位。</span><span class="sxs-lookup"><span data-stu-id="64705-115">Specifies the parity bit for a <xref:System.IO.Ports.SerialPort> object.</span></span>|  
|<xref:System.IO.Ports.SerialData>|<span data-ttu-id="64705-116">指定在 <xref:System.IO.Ports.SerialPort> 对象的串行端口上收到的字符的类型。</span><span class="sxs-lookup"><span data-stu-id="64705-116">Specifies the type of character that was received on the serial port of the <xref:System.IO.Ports.SerialPort> object.</span></span>|  
|<xref:System.IO.Ports.SerialError>|<span data-ttu-id="64705-117">指定在 <xref:System.IO.Ports.SerialPort> 对象上发生的错误</span><span class="sxs-lookup"><span data-stu-id="64705-117">Specifies errors that occur on the <xref:System.IO.Ports.SerialPort> object</span></span>|  
|<xref:System.IO.Ports.SerialPinChange>|<span data-ttu-id="64705-118">指定在 <xref:System.IO.Ports.SerialPort> 对象上发生的更改的类型。</span><span class="sxs-lookup"><span data-stu-id="64705-118">Specifies the type of change that occurred on the <xref:System.IO.Ports.SerialPort> object.</span></span>|  
|<xref:System.IO.Ports.StopBits>|<span data-ttu-id="64705-119">指定在 <xref:System.IO.Ports.SerialPort> 对象上使用的停止位的数目。</span><span class="sxs-lookup"><span data-stu-id="64705-119">Specifies the number of stop bits used on the <xref:System.IO.Ports.SerialPort> object.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="64705-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="64705-120">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Devices.Ports>  
 [<span data-ttu-id="64705-121">访问计算机的端口</span><span class="sxs-lookup"><span data-stu-id="64705-121">Accessing the Computer's Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/accessing-the-computer-s-ports.md)
