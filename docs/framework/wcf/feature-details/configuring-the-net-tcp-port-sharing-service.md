---
title: 配置 Net.TCP 端口共享服务
ms.date: 03/30/2017
ms.assetid: b6dd81fa-68b7-4e1b-868e-88e5901b7ea0
ms.openlocfilehash: 9bc625f9e998f27b6227a5951f11c7d85220ae7f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54585518"
---
# <a name="configuring-the-nettcp-port-sharing-service"></a><span data-ttu-id="c5b13-102">配置 Net.TCP 端口共享服务</span><span class="sxs-lookup"><span data-stu-id="c5b13-102">Configuring the Net.TCP Port Sharing Service</span></span>
<span data-ttu-id="c5b13-103">使用 Net.TCP 传输协议的自承载服务可以控制某些高级设置，如 `ListenBacklog` 和 `MaxPendingAccepts`，这些设置控制用作网络通信的基础 TCP 套接字的行为。</span><span class="sxs-lookup"><span data-stu-id="c5b13-103">Self-hosted services that use the Net.TCP transport can control several advanced settings, such as `ListenBacklog` and `MaxPendingAccepts`, which govern the behavior of the underlying TCP socket used for network communication.</span></span> <span data-ttu-id="c5b13-104">但是，如果传输绑定已禁用端口共享（默认情况下是启用的），则这些针对每个套接字的设置将仅在绑定级别适用。</span><span class="sxs-lookup"><span data-stu-id="c5b13-104">However, these settings for each socket only apply at the binding level if the transport binding has disabled port sharing, which is enabled by default.</span></span>  
  
 <span data-ttu-id="c5b13-105">当 net.tcp 绑定启用端口共享时（通过在传输绑定元素上设置 `portSharingEnabled =true` 来实现），该绑定隐式允许外部进程（即承载 Net.TCP 端口共享服务的 SMSvcHost.exe）代表它来管理 TCP 套接字。</span><span class="sxs-lookup"><span data-stu-id="c5b13-105">When a net.tcp binding enables port sharing (by setting `portSharingEnabled =true` on the transport binding element), it implicitly allows an external process (namely the SMSvcHost.exe, which hosts the Net.TCP Port Sharing Service) to manage the TCP socket on its behalf.</span></span> <span data-ttu-id="c5b13-106">例如，使用 TCP 时指定：</span><span class="sxs-lookup"><span data-stu-id="c5b13-106">For example, when using TCP, specify:</span></span>  
  
```xml  
<tcpTransport portSharingEnabled="true"  />  
```  
  
 <span data-ttu-id="c5b13-107">如果按这种方式进行配置，则会忽略在服务的传输绑定元素上指定的任何套接字设置，而代之以由 SMSvcHost.exe 指定的套接字设置。</span><span class="sxs-lookup"><span data-stu-id="c5b13-107">When configured in this way, any socket settings specified on the service's transport binding element are ignored in favor of the socket settings specified by SMSvcHost.exe.</span></span>  
  
 <span data-ttu-id="c5b13-108">若要配置 SMSvcHost.exe，请创建一个名为 SmSvcHost.exe.config 的 XML 配置文件，并将其与 SMSvcHost.exe 可执行文件放在同一个物理目录中（例如，C:\Windows\Microsoft.NET\Framework\v4.5）。</span><span class="sxs-lookup"><span data-stu-id="c5b13-108">To configure the SMSvcHost.exe, create an XML configuration file named SmSvcHost.exe.config and place it in the same physical directory as the SMSvcHost.exe executable (for example, C:\Windows\Microsoft.NET\Framework\v4.5).</span></span>  
  
 <span data-ttu-id="c5b13-109">下面的示例阐释了示例 SMSvcHost.exe.config 并对所有显式指定的可配置值使用默认设置。</span><span class="sxs-lookup"><span data-stu-id="c5b13-109">The following example illustrates a sample SMSvcHost.exe.config, with the default settings for all configurable values stated explicitly.</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <net.tcp listenBacklog="16" <!--16 * # of processors -->  
          maxPendingAccepts="4"<!-- 4 * # of processors -->  
          maxPendingConnections="100"  
          receiveTimeout="00:00:30" <!--30 seconds -->  
          teredoEnabled="false">  
          <allowAccounts>  
             <!-- LocalSystem account -->  
             <add securityIdentifier="S-1-5-18"/>  
             <!-- LocalService account -->  
             <add securityIdentifier="S-1-5-19"/>  
             <!-- Administrators account -->  
             <add securityIdentifier="S-1-5-20"/>  
             <!-- Network Service account -->  
             <add securityIdentifier="S-1-5-32-544" />  
             <!-- IIS_IUSRS account (Vista only) -->  
             <add securityIdentifier="S-1-5-32-568"/>  
           </allowAccounts>  
       </net.tcp>  
</configuration>  
```  
  
## <a name="when-to-modify-smsvchostexeconfig"></a><span data-ttu-id="c5b13-110">何时修改 SMSvcHost.exe.config</span><span class="sxs-lookup"><span data-stu-id="c5b13-110">When to Modify SMSvcHost.exe.config</span></span>  
 <span data-ttu-id="c5b13-111">通常，修改 SMSvcHost.exe.config 文件的内容时应当小心，原因是此文件中指定的任何配置设置都会影响使用 Net.TCP 端口共享服务的计算机上的所有服务。</span><span class="sxs-lookup"><span data-stu-id="c5b13-111">In general, care should be taken when modifying the contents of the SMSvcHost.exe.config file, because any configuration settings specified in this file affect all of the services on a computer that uses the Net.TCP Port Sharing Service.</span></span> <span data-ttu-id="c5b13-112">这包括 [!INCLUDE[wv](../../../../includes/wv-md.md)] 上使用 Windows 进程激活服务 (WAS) 的 TCP 激活功能的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c5b13-112">This includes applications on [!INCLUDE[wv](../../../../includes/wv-md.md)] that use the TCP Activation features of the Windows Process Activation Service (WAS).</span></span>  
  
 <span data-ttu-id="c5b13-113">但是，有时可能需要更改 Net.TCP 端口共享服务的默认配置。</span><span class="sxs-lookup"><span data-stu-id="c5b13-113">However, sometimes you may need to change the default configuration for the Net.TCP Port Sharing Service.</span></span> <span data-ttu-id="c5b13-114">例如，`maxPendingAccepts` 的默认值为 4 \* 处理器数。</span><span class="sxs-lookup"><span data-stu-id="c5b13-114">For example, the default value for `maxPendingAccepts` is 4 \* number of processors.</span></span> <span data-ttu-id="c5b13-115">承载大量使用端口共享的服务的服务器可以增加此值，以实现最大的吞吐量。</span><span class="sxs-lookup"><span data-stu-id="c5b13-115">Servers that host a large number of services that use port sharing may increase this value to achieve maximum throughput.</span></span> <span data-ttu-id="c5b13-116">`maxPendingConnections` 的默认值为 100。</span><span class="sxs-lookup"><span data-stu-id="c5b13-116">The default value for `maxPendingConnections` is 100.</span></span> <span data-ttu-id="c5b13-117">如果有多个并发客户端调用服务，并且此服务正在丢弃客户端连接，您还应该考虑增加此值。</span><span class="sxs-lookup"><span data-stu-id="c5b13-117">You should consider increasing this value also if there are multiple concurrent clients calling the service and the service is dropping client connections.</span></span>  
  
 <span data-ttu-id="c5b13-118">SMSvcHost.exe.config 还包含有关可以使用端口共享服务的进程标识的信息。</span><span class="sxs-lookup"><span data-stu-id="c5b13-118">SMSvcHost.exe.config also contains information about the process identities that may make use of the port sharing service.</span></span> <span data-ttu-id="c5b13-119">当进程连接到端口共享服务以使用共享的 TCP 端口时，将根据允许使用端口共享服务的标识列表来检查连接进程的进程标识。</span><span class="sxs-lookup"><span data-stu-id="c5b13-119">When a process connects to the port sharing service to make use of a shared TCP port, the process identity of the connecting process is checked against a list of identities that are permitted to make use of the port sharing service.</span></span> <span data-ttu-id="c5b13-120">这些标识作为安全标识符 (Sid) 指定在\<allowAccounts > 在 SMSvcHost.exe.config 文件的部分。</span><span class="sxs-lookup"><span data-stu-id="c5b13-120">These identities are specified as security identifiers (SIDs) in the \<allowAccounts> section of the SMSvcHost.exe.config file.</span></span> <span data-ttu-id="c5b13-121">默认情况下，将授予系统帐户（LocalService、LocalSystem 和 NetworkService）和 Administrators 组的成员使用端口共享服务的权限。</span><span class="sxs-lookup"><span data-stu-id="c5b13-121">By default, permission to use the port sharing service is granted to system accounts (LocalService, LocalSystem, and NetworkService) as well as members of the Administrators group.</span></span> <span data-ttu-id="c5b13-122">允许作为另一个标识（例如，用户标识）运行的进程连接到端口共享服务的应用程序必须将适当的 SID 显式添加到 SMSvcHost.exe.config 中（在重新启动 SMSvc.exe 进程之前不会应用这些更改）。</span><span class="sxs-lookup"><span data-stu-id="c5b13-122">Applications that allow a process running as another identity (for example, a user identity) to connect to the port sharing service must explicitly add the appropriate SID to the SMSvcHost.exe.config (these changes are not applied until the SMSvc.exe process is restarted).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c5b13-123">在启用用户帐户控制 (UAC) 的 [!INCLUDE[wv](../../../../includes/wv-md.md)] 系统上，即使本地用户的帐户是 Administrators 组成员，本地用户也需要提升的权限。</span><span class="sxs-lookup"><span data-stu-id="c5b13-123">On [!INCLUDE[wv](../../../../includes/wv-md.md)] systems with User Account Control (UAC) enabled, local users require elevated permissions even if their account is a member of the Administrators group.</span></span> <span data-ttu-id="c5b13-124">若要允许这些用户必须使用端口共享服务而无需提升用户的 SID （或用户所属组的 SID） 显式添加到\<allowAccounts > SMSvcHost.exe.config 的部分。</span><span class="sxs-lookup"><span data-stu-id="c5b13-124">To allow these users to make use of the port sharing service without elevation, the user's SID (or the SID of a group in which the user is a member) must be explicitly added to the \<allowAccounts> section of SMSvcHost.exe.config.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="c5b13-125">默认 SMSvcHost.exe.config 文件指定自定义 `etwProviderId` 以阻止 SMSvcHost.exe 跟踪干扰服务跟踪。</span><span class="sxs-lookup"><span data-stu-id="c5b13-125">The default SMSvcHost.exe.config file specifies a custom `etwProviderId` to prevent SMSvcHost.exe tracing from interfering with service traces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5b13-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5b13-126">See also</span></span>
- [<span data-ttu-id="c5b13-127">\<net.tcp></span><span class="sxs-lookup"><span data-stu-id="c5b13-127">\<net.tcp></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)
