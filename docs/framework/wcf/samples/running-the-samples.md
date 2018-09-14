---
title: 运行 Windows Communication Foundation 示例
ms.date: 03/30/2017
ms.assetid: db8a83da-95c1-4a21-a9d2-48caeb6398ea
ms.openlocfilehash: d6fc93af217bfc282ce7030973be32baf7d864cd
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2018
ms.locfileid: "45618687"
---
# <a name="running-the-windows-communication-foundation-samples"></a><span data-ttu-id="cb6a9-102">运行 Windows Communication Foundation 示例</span><span class="sxs-lookup"><span data-stu-id="cb6a9-102">Running the Windows Communication Foundation Samples</span></span>
<span data-ttu-id="cb6a9-103">可以在单一计算机或跨计算机配置中运行的 Windows Communication Foundation (WCF) 示例。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-103">The Windows Communication Foundation (WCF) samples can be run in a single-machine or cross-machine configuration.</span></span> <span data-ttu-id="cb6a9-104">示例在提供时就可用于在单机上运行。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-104">As supplied, the samples are ready for running on a single machine.</span></span> <span data-ttu-id="cb6a9-105">在跨计算机配置中，必须修改示例的配置文件设置。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-105">In a cross-machine configuration, it is necessary to modify a sample's configuration file settings.</span></span> <span data-ttu-id="cb6a9-106">下面的过程说明如何用同一计算机配置和跨计算机配置来运行示例。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-106">The following procedures explain how to run a sample in same-machine and cross-machine configurations.</span></span> <span data-ttu-id="cb6a9-107">请注意，Internet 信息服务 (IIS) 中承载的服务和自承载示例在步骤上有所不同。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-107">Note that there are variations in the steps for services hosted in Internet Information Services (IIS) and the self-hosted samples.</span></span> <span data-ttu-id="cb6a9-108">大多数示例承载于 IIS 中，请参见示例自述文件信息以确定示例的承载方式。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-108">Most samples are hosted in IIS; see the sample readme information to determine how it is hosted.</span></span>  
  
 <span data-ttu-id="cb6a9-109">在 [!INCLUDE[wv](../../../../includes/wv-md.md)] 上，未在 IIS 中承载的示例需要提升的权限以使用 Http.sys 注册侦听器。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-109">On [!INCLUDE[wv](../../../../includes/wv-md.md)], samples that are not hosted in IIS require elevated privileges to register a listener with Http.sys.</span></span> <span data-ttu-id="cb6a9-110">以服务运行所用的帐户使用 Httpcfg.exe 注册服务侦听地址，或从以管理员特权运行的命令提示符启动服务。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-110">Use Httpcfg.exe to register the service's listening addresses with the account the service is running under, or launch the service from a command prompt running with administrator privileges.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb6a9-111">在生成或运行任何 WCF 示例之前, 请确保您已执行了[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-111">Before building or running any of the WCF samples, be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
### <a name="to-run-the-sample-on-the-same-machine"></a><span data-ttu-id="cb6a9-112">在同一计算机上运行示例</span><span class="sxs-lookup"><span data-stu-id="cb6a9-112">To run the sample on the same machine</span></span>  
  
1.  <span data-ttu-id="cb6a9-113">如果服务由 IIS 承载，请确保您可以访问使用浏览器通过输入以下地址的服务： http://localhost/servicemodelsamples/service.svc。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-113">If the service is hosted by IIS, ensure that you can access the service using a browser by entering the following address: http://localhost/servicemodelsamples/service.svc.</span></span> <span data-ttu-id="cb6a9-114">在响应中应显示确认页。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-114">A confirmation page should be displayed in response.</span></span> <span data-ttu-id="cb6a9-115">如果未显示确认页，请参阅[故障排除提示](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-115">If the confirmation page is not displayed, see [Troubleshooting Tips](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
2.  <span data-ttu-id="cb6a9-116">如果服务是自承载的，请从 \service\bin（在语言特定文件夹内）中运行 Service.exe。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-116">If the service is self-hosted, run Service.exe from \service\bin, from under the language-specific folder.</span></span> <span data-ttu-id="cb6a9-117">服务活动显示在服务控制台窗口上。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-117">Service activity is displayed on the service console window.</span></span>  
  
3.  <span data-ttu-id="cb6a9-118">从 \client\bin 运行 Client.exe\\，从特定于语言的文件夹下。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-118">Run Client.exe from \client\bin\\, from under the language-specific folder.</span></span> <span data-ttu-id="cb6a9-119">客户端活动将显示在客户端控制台窗口上。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-119">Client activity is displayed on the client console window.</span></span>  
  
4.  <span data-ttu-id="cb6a9-120">如果客户端和服务能够进行通信，请参见[故障排除提示](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-120">If the client and service are not able to communicate, see [Troubleshooting Tips](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
### <a name="to-run-the-sample-across-machines"></a><span data-ttu-id="cb6a9-121">跨计算机运行示例</span><span class="sxs-lookup"><span data-stu-id="cb6a9-121">To run the sample across machines</span></span>  
  
1.  <span data-ttu-id="cb6a9-122">如果服务在 IIS 中承载：</span><span class="sxs-lookup"><span data-stu-id="cb6a9-122">If the service is hosted in IIS:</span></span>  
  
    1.  <span data-ttu-id="cb6a9-123">在服务计算机上创建一个名为 ServiceModelSamples 的虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-123">On the service machine, create a virtual directory named ServiceModelSamples.</span></span> <span data-ttu-id="cb6a9-124">批处理文件 Setupvroot.bat 附带[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)可用于创建磁盘目录和虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-124">The batch file Setupvroot.bat included with [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md) can be used to create the disk directory and virtual directory.</span></span>  
  
    2.  <span data-ttu-id="cb6a9-125">从 %SystemDrive%\Inetpub\wwwroot\servicemodelsamples 中将服务程序文件复制到服务计算机上的 ServiceModelSamples 虚拟目录中。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-125">Copy the service program files from %SystemDrive%\Inetpub\wwwroot\servicemodelsamples to the ServiceModelSamples virtual directory on the service machine.</span></span> <span data-ttu-id="cb6a9-126">确保在 \bin 目录中包括这些文件。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-126">Ensure that you include the files in the \bin directory.</span></span>  
  
    3.  <span data-ttu-id="cb6a9-127">测试是否可使用浏览器从客户端计算机访问服务。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-127">Test that you can access the service from the client machine using a browser.</span></span>  
  
     <span data-ttu-id="cb6a9-128">如果服务是自承载的：</span><span class="sxs-lookup"><span data-stu-id="cb6a9-128">If the service is self-hosted:</span></span>  
  
    1.  <span data-ttu-id="cb6a9-129">在服务计算机上，创建一个保存服务文件的目录。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-129">On the service machine, create a directory to hold the service files.</span></span>  
  
    2.  <span data-ttu-id="cb6a9-130">将 \service\bin\ 文件夹（在语言特定文件夹内）中的服务程序文件复制到服务计算机上。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-130">Copy the service program files from the \service\bin\ folder, under the language-specific folder, to the service machine.</span></span>  
  
    3.  <span data-ttu-id="cb6a9-131">在服务配置文件中，更改终结点定义的地址值以与服务的新地址相匹配。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-131">In the service configuration file, change the address value of the endpoint definition to match the new address of your service.</span></span> <span data-ttu-id="cb6a9-132">在地址中将任何对“localhost”的引用替换为一个完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-132">Replace any references to "localhost" with a fully-qualified domain name in the address.</span></span>  
  
    4.  <span data-ttu-id="cb6a9-133">在命令提示符处启动 Service.exe。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-133">Launch Service.exe from a command prompt.</span></span>  
  
2.  <span data-ttu-id="cb6a9-134">将 \client\bin\ 文件夹（在语言特定文件夹内）中的客户端程序文件复制到客户端计算机上。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-134">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client machine.</span></span>  
  
3.  <span data-ttu-id="cb6a9-135">设置终结点地址。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-135">Set the endpoint address.</span></span>  
  
    1.  <span data-ttu-id="cb6a9-136">如果服务未在域帐户下运行，请打开客户端配置文件并更改终结点定义的地址值以与服务的新地址相匹配。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-136">If the service is not running under a domain account, open the client configuration file and change the address value of the endpoint definition to match the new address of your service.</span></span> <span data-ttu-id="cb6a9-137">在地址中将任何对“localhost”的引用替换为一个完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-137">Replace any references to "localhost" with a fully-qualified domain name in the address.</span></span>  
  
    2.  <span data-ttu-id="cb6a9-138">如果服务正在域帐户下运行，则通过针对服务运行 Svcutil.exe 来重新生成客户端配置。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-138">If the service is running under a domain account, regenerate the client configuration by running Svcutil.exe against the service.</span></span> <span data-ttu-id="cb6a9-139">有关运行 Svcutil.exe 的详细信息，请参阅[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-139">For more information about running Svcutil.exe, see [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span> <span data-ttu-id="cb6a9-140">使用生成的文件来代替示例中的配置文件。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-140">Use the generated file instead of the configuration file in the sample.</span></span> <span data-ttu-id="cb6a9-141">生成的配置文件有附加的标识信息，并包含连接到服务终结点所需的所有设置，即使这些设置是默认设置。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-141">The generated configuration file has additional identity information, and contains all settings necessary to connect to the service endpoint even though they are the default settings.</span></span> <span data-ttu-id="cb6a9-142">有关标识信息的详细信息，请参阅[服务标识和身份验证](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)，并[\<标识 >](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-142">For more information about identity information, see [Service Identity and Authentication](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md), and [\<identity>](../../../../docs/framework/configure-apps/file-schema/wcf/identity.md).</span></span>  
  
4.  <span data-ttu-id="cb6a9-143">在客户端计算机上，在命令提示符下启动 Client.exe。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-143">On the client machine, launch Client.exe from a command prompt.</span></span>  
  
### <a name="to-debug-a-service"></a><span data-ttu-id="cb6a9-144">调试服务</span><span class="sxs-lookup"><span data-stu-id="cb6a9-144">To debug a service</span></span>  
  
1.  <span data-ttu-id="cb6a9-145">生成解决方案 （客户端和服务） 使用**生成**菜单或 CTRL + SHIFT + B。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-145">Build the solution (both client and service) using the **Build** menu or CTRL+SHIFT+B.</span></span>  
  
2.  <span data-ttu-id="cb6a9-146">如果服务在 IIS 中承载：</span><span class="sxs-lookup"><span data-stu-id="cb6a9-146">If the service is hosted in IIS:</span></span>  
  
    1.  <span data-ttu-id="cb6a9-147">激活服务使用的浏览器通过输入地址 http://localhost/servicemodelsamples/service.svc。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-147">Activate the service using a browser by entering the address http://localhost/servicemodelsamples/service.svc.</span></span>  
  
    2.  <span data-ttu-id="cb6a9-148">在解决方案中，选择**调试**菜单并**附加到进程**菜单项。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-148">In the solution, choose the **Debug** menu and the **Attach to Process** menu item.</span></span>  
  
    3.  <span data-ttu-id="cb6a9-149">选择“显示所有用户的进程”复选框。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-149">Select the **Show processes from all users** check box.</span></span>  
  
    4.  <span data-ttu-id="cb6a9-150">选择主机辅助进程 W3wp.exe 以进行调试（在 Windows XP 上选择 ASPNet_wp.exe on）。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-150">Select the host worker process W3wp.exe to debug (select ASPNet_wp.exe on Windows XP).</span></span>  
  
3.  <span data-ttu-id="cb6a9-151">现在可以在服务代码中设置断点并启用针对异常的断点。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-151">You can now set breakpoints in the service code and enable breakpoints on exceptions.</span></span>  
  
4.  <span data-ttu-id="cb6a9-152">右键单击客户端项目项，然后选择**调试**，**启动新实例**。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-152">Right-click the client project item and choose **Debug**, **Start new instance**.</span></span>  
  
### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="cb6a9-153">运行示例后进行清理</span><span class="sxs-lookup"><span data-stu-id="cb6a9-153">To clean up after the sample</span></span>  
  
-   <span data-ttu-id="cb6a9-154">出于安全目的，如果服务承载于 IIS 中，请在示例结束后删除虚拟目录定义和在安装步骤中授予的权限。</span><span class="sxs-lookup"><span data-stu-id="cb6a9-154">If the service is hosted in IIS for security purposes, remove the virtual directory definition and permissions granted in the setup steps when you are finished with the samples.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb6a9-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="cb6a9-155">See Also</span></span>  
 [<span data-ttu-id="cb6a9-156">生成 Windows Communication Foundation 示例</span><span class="sxs-lookup"><span data-stu-id="cb6a9-156">Building the Windows Communication Foundation Samples</span></span>](../../../../docs/framework/wcf/samples/building-the-samples.md)  
 [<span data-ttu-id="cb6a9-157">在工作组中和跨计算机运行示例</span><span class="sxs-lookup"><span data-stu-id="cb6a9-157">Running the Samples in a Workgroup and Across Machines</span></span>](https://msdn.microsoft.com/library/a451a525-e7ce-452d-9da9-620221260113)  
 [<span data-ttu-id="cb6a9-158">疑难解答提示</span><span class="sxs-lookup"><span data-stu-id="cb6a9-158">Troubleshooting Tips</span></span>](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)
