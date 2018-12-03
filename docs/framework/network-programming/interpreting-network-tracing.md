---
title: 解释网络跟踪
ms.date: 03/30/2017
helpviewer_keywords:
- TraceMode attribute
- hexidecimal data, network tracing output
- network tracing, analyzing
- protocolonly
- text, network tracing output
- includehex
ms.assetid: ad22b4b8-00af-4778-9cca-cb609ce1f8ff
ms.openlocfilehash: 94a64efcd7b4f354eaa22d1b646f36212f9c8fbb
ms.sourcegitcommit: 7f7664837d35320a0bad3f7e4ecd68d6624633b2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/30/2018
ms.locfileid: "52672288"
---
# <a name="interpreting-network-tracing"></a><span data-ttu-id="7f806-102">解释网络跟踪</span><span class="sxs-lookup"><span data-stu-id="7f806-102">Interpreting Network Tracing</span></span>
<span data-ttu-id="7f806-103">启用网络跟踪之后，可以通过跟踪捕获应用程序对各种 <xref:System.Net> 类成员的调用。</span><span class="sxs-lookup"><span data-stu-id="7f806-103">When network tracing is enabled, you can use tracing to capture calls your application makes to various <xref:System.Net> class members.</span></span> <span data-ttu-id="7f806-104">这些调用的输出可能类似于以下示例。</span><span class="sxs-lookup"><span data-stu-id="7f806-104">The output from these calls may be similar to the following examples.</span></span>  
  
```  
[588]   (4357)   Entering Socket#33574638::Send()  
[588]   (4387)   Exiting Socket#33574638::Send()-> 61#61  
```  
  
 <span data-ttu-id="7f806-105">在上一示例中，[588] 是当前线程的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="7f806-105">In the preceding example, [588] is the current thread's unique identifier.</span></span> <span data-ttu-id="7f806-106">(4357) 和 (4387) 是一种时间戳，它表示应用程序启动以来已经经过的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="7f806-106">(4357) and (4387) are timestamps denoting the number of milliseconds that have elapsed since the application started.</span></span> <span data-ttu-id="7f806-107">时间戳之后的数据显示了进入和退出“Socket.Send”方法的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7f806-107">The data following the timestamp shows the application entering and exiting the method **Socket.Send**.</span></span> <span data-ttu-id="7f806-108">执行“Send”方法的对象使用 33574638 作为其唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="7f806-108">The object executing the **Send** method has 33574638 as its unique identifier.</span></span> <span data-ttu-id="7f806-109">退出跟踪方法包括返回值（上一示例中为 61）。</span><span class="sxs-lookup"><span data-stu-id="7f806-109">The method exit trace includes the return value (61 in the preceding example).</span></span>  
  
 <span data-ttu-id="7f806-110">网络跟踪可以使用诸如 Hypertext Transfer Protocol (HTTP) 应用程序级协议捕获由应用程序发送或接收的网络流量。</span><span class="sxs-lookup"><span data-stu-id="7f806-110">Network traces can capture network traffic that is sent from or received by your application using application-level protocols such as Hypertext Transfer Protocol (HTTP).</span></span> <span data-ttu-id="7f806-111">此数据可捕获为文本或十六进制数据。</span><span class="sxs-lookup"><span data-stu-id="7f806-111">This data can be captured as text and, optionally, hexadecimal data.</span></span> <span data-ttu-id="7f806-112">如果将“includehex”指定为“tracemode”属性的值，可使用十六进制数据。</span><span class="sxs-lookup"><span data-stu-id="7f806-112">Hexadecimal data is available when you specify **includehex** as the value of the **tracemode** attribute.</span></span> <span data-ttu-id="7f806-113">（有关此属性的详细信息，请参阅[如何：配置网络跟踪](../../../docs/framework/network-programming/how-to-configure-network-tracing.md)。）下例通过“includehex”生成跟踪。</span><span class="sxs-lookup"><span data-stu-id="7f806-113">(For detailed information about this attribute, see [How to: Configure Network Tracing](../../../docs/framework/network-programming/how-to-configure-network-tracing.md).) The following example trace was generated using **includehex**.</span></span>  
  
 `[1692]   (1142)   00000000 : 47 45 54 20 2F 77 70 61-64 2E 64 61 74 20 48 54 : GET /wpad.dat HT`  
  
 `[1692]   (1142)   00000010 : 54 50 2F 31 2E 31 0D 0A-48 6F 73 74 3A 20 69 74 : TP/1.1..Host: it`  
  
 `[1692]   (1142)   00000020 : 67 70 72 6F 78 79 0D 0A-43 6F 6E 6E 65 63 74 69 : gproxy..Connecti`  
  
 `[1692]   (1142)   00000030 : 6F 6E 3A 20 43 6C 6F 73-65 0D 0A 0D 0A     : on: Close....`  
  
 <span data-ttu-id="7f806-114">若要省略十六进制数据，请将“protocolonly”指定为“tracemode”属性的值。</span><span class="sxs-lookup"><span data-stu-id="7f806-114">To omit hexadecimal data, specify **protocolonly** as the value for the **tracemode** attribute.</span></span> <span data-ttu-id="7f806-115">下例演示了指定“protocolonly”时的跟踪。</span><span class="sxs-lookup"><span data-stu-id="7f806-115">The following example shows the trace when **protocolonly** is specified.</span></span>  
  
 `[2444]   (594)   Data from ConnectStream#33574638::WriteHeaders<<GET /wpad.dat HTTP/1.1`  
  
 `Host: itgproxy`  
  
 `Connection: Close`  
  
## <a name="see-also"></a><span data-ttu-id="7f806-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="7f806-116">See Also</span></span>  
 [<span data-ttu-id="7f806-117">启用网络跟踪</span><span class="sxs-lookup"><span data-stu-id="7f806-117">Enabling Network Tracing</span></span>](../../../docs/framework/network-programming/enabling-network-tracing.md)  
 [<span data-ttu-id="7f806-118">如何：配置网络跟踪</span><span class="sxs-lookup"><span data-stu-id="7f806-118">How to: Configure Network Tracing</span></span>](../../../docs/framework/network-programming/how-to-configure-network-tracing.md)  
 [<span data-ttu-id="7f806-119">.NET Framework 中的网络跟踪</span><span class="sxs-lookup"><span data-stu-id="7f806-119">Network Tracing in the .NET Framework</span></span>](../../../docs/framework/network-programming/network-tracing.md)
