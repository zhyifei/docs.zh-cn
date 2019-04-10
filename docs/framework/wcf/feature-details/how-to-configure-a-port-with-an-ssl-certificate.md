---
title: 如何：使用 SSL 证书配置端口
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SSL
- WCF, security mode
- WCF, security
ms.assetid: b8abcc8e-a5f5-4317-aca5-01e3c40ab24d
ms.openlocfilehash: d709123895f361c1d2268a218b4163c8d195e1b4
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59345581"
---
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a><span data-ttu-id="a73ec-102">如何：使用 SSL 证书配置端口</span><span class="sxs-lookup"><span data-stu-id="a73ec-102">How to: Configure a Port with an SSL Certificate</span></span>
<span data-ttu-id="a73ec-103">创建使用自承载的 Windows Communication Foundation (WCF) 服务时<xref:System.ServiceModel.WSHttpBinding>类，使用传输安全，还必须使用 X.509 证书配置端口。</span><span class="sxs-lookup"><span data-stu-id="a73ec-103">When creating a self-hosted Windows Communication Foundation (WCF) service with the <xref:System.ServiceModel.WSHttpBinding> class that uses transport security, you must also configure a port with an X.509 certificate.</span></span> <span data-ttu-id="a73ec-104">如果不是在创建自承载服务，可以在 Internet 信息服务 (IIS) 上承载服务。</span><span class="sxs-lookup"><span data-stu-id="a73ec-104">If you are not creating a self-hosted service, you can host your service on Internet Information Services (IIS).</span></span> <span data-ttu-id="a73ec-105">有关详细信息，请参阅[HTTP 传输安全性](../../../../docs/framework/wcf/feature-details/http-transport-security.md)。</span><span class="sxs-lookup"><span data-stu-id="a73ec-105">For more information, see [HTTP Transport Security](../../../../docs/framework/wcf/feature-details/http-transport-security.md).</span></span>  
  
 <span data-ttu-id="a73ec-106">若要配置端口，使用的工具取决于计算机运行的操作系统。</span><span class="sxs-lookup"><span data-stu-id="a73ec-106">To configure a port, the tool you use depends on the operating system that is running on your machine.</span></span>  
  
 <span data-ttu-id="a73ec-107">如果运行的是 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 或 [!INCLUDE[wxp](../../../../includes/wxp-md.md)]，则使用 HttpCfg.exe 工具。</span><span class="sxs-lookup"><span data-stu-id="a73ec-107">If you are running [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool.</span></span> <span data-ttu-id="a73ec-108">[!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 中已安装该工具。</span><span class="sxs-lookup"><span data-stu-id="a73ec-108">With [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] this tool is installed.</span></span> <span data-ttu-id="a73ec-109">与[!INCLUDE[wxp](../../../../includes/wxp-md.md)]，可以下载该工具在[Windows XP Service Pack 2 支持工具](https://go.microsoft.com/fwlink/?LinkId=88606)。</span><span class="sxs-lookup"><span data-stu-id="a73ec-109">With [!INCLUDE[wxp](../../../../includes/wxp-md.md)], you can download the tool at [Windows XP Service Pack 2 Support Tools](https://go.microsoft.com/fwlink/?LinkId=88606).</span></span> <span data-ttu-id="a73ec-110">有关详细信息，请参阅[Httpcfg 概述](https://go.microsoft.com/fwlink/?LinkId=88605)。</span><span class="sxs-lookup"><span data-stu-id="a73ec-110">For more information, see [Httpcfg Overview](https://go.microsoft.com/fwlink/?LinkId=88605).</span></span> <span data-ttu-id="a73ec-111">[Windows 支持工具文档](https://go.microsoft.com/fwlink/?LinkId=94840)说明了 Httpcfg.exe 工具的语法。</span><span class="sxs-lookup"><span data-stu-id="a73ec-111">The [Windows Support Tools documentation](https://go.microsoft.com/fwlink/?LinkId=94840) explains the syntax for the Httpcfg.exe tool.</span></span>  
  
 <span data-ttu-id="a73ec-112">如果运行的是 [!INCLUDE[wv](../../../../includes/wv-md.md)]，则使用已安装的 Netsh.exe 工具。</span><span class="sxs-lookup"><span data-stu-id="a73ec-112">If you are running [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool that is already installed.</span></span>  
  
 <span data-ttu-id="a73ec-113">本主题介绍如何完成以下一些过程：</span><span class="sxs-lookup"><span data-stu-id="a73ec-113">This topic describes how to accomplish several procedures:</span></span>  
  
-   <span data-ttu-id="a73ec-114">确定计算机当前的端口配置。</span><span class="sxs-lookup"><span data-stu-id="a73ec-114">Determining a computer's current port configuration.</span></span>  
  
-   <span data-ttu-id="a73ec-115">获取证书的指纹（以下两个过程需要证书指纹）。</span><span class="sxs-lookup"><span data-stu-id="a73ec-115">Getting a certificate's thumbprint (necessary for the following two procedures).</span></span>  
  
-   <span data-ttu-id="a73ec-116">将 SSL 证书绑定到端口配置。</span><span class="sxs-lookup"><span data-stu-id="a73ec-116">Binding an SSL certificate to a port configuration.</span></span>  
  
-   <span data-ttu-id="a73ec-117">将 SSL 证书绑定到端口配置并支持客户端证书。</span><span class="sxs-lookup"><span data-stu-id="a73ec-117">Binding an SSL certificate to a port configuration and supporting client certificates.</span></span>  
  
-   <span data-ttu-id="a73ec-118">从某个端口号删除 SSL 证书。</span><span class="sxs-lookup"><span data-stu-id="a73ec-118">Deleting an SSL certificate from a port number.</span></span>  
  
 <span data-ttu-id="a73ec-119">请注意，修改存储于计算机上的证书需要管理特权。</span><span class="sxs-lookup"><span data-stu-id="a73ec-119">Note that modifying certificates stored on the computer requires administrative privileges.</span></span>  
  
### <a name="to-determine-how-ports-are-configured"></a><span data-ttu-id="a73ec-120">确定如何配置端口</span><span class="sxs-lookup"><span data-stu-id="a73ec-120">To determine how ports are configured</span></span>  
  
1. <span data-ttu-id="a73ec-121">在中[!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]或[!INCLUDE[wxp](../../../../includes/wxp-md.md)]，使用 HttpCfg.exe 工具查看当前端口配置中，使用**查询**并**ssl**切换时，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="a73ec-121">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool to view the current port configuration, using the **query** and **ssl** switches, as shown in the following example.</span></span>  
  
    ```  
    httpcfg query ssl  
    ```  
  
2. <span data-ttu-id="a73ec-122">在 [!INCLUDE[wv](../../../../includes/wv-md.md)] 中，使用 Netsh.exe 工具查看当前端口配置，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="a73ec-122">In [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool to view the current port configuration, as shown in the following example.</span></span>  
  
    ```  
    netsh http show sslcert  
    ```  
  
### <a name="to-get-a-certificates-thumbprint"></a><span data-ttu-id="a73ec-123">获取证书的指纹</span><span class="sxs-lookup"><span data-stu-id="a73ec-123">To get a certificate's thumbprint</span></span>  
  
1. <span data-ttu-id="a73ec-124">使用证书 MMC 管理单元查找用于客户端身份验证的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="a73ec-124">Use the Certificates MMC snap-in to find an X.509 certificate that has an intended purpose of client authentication.</span></span> <span data-ttu-id="a73ec-125">有关详细信息，请参阅[如何：使用 MMC 管理单元查看证书](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)。</span><span class="sxs-lookup"><span data-stu-id="a73ec-125">For more information, see [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
2. <span data-ttu-id="a73ec-126">访问证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="a73ec-126">Access the certificate's thumbprint.</span></span> <span data-ttu-id="a73ec-127">有关详细信息，请参阅[如何：检索证书的指纹](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)。</span><span class="sxs-lookup"><span data-stu-id="a73ec-127">For more information, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
3. <span data-ttu-id="a73ec-128">将证书指纹复制到文本编辑器，如 Notepad。</span><span class="sxs-lookup"><span data-stu-id="a73ec-128">Copy the thumbprint of the certificate into a text editor, such as Notepad.</span></span>  
  
4. <span data-ttu-id="a73ec-129">移除十六进制字符之间的所有空格。</span><span class="sxs-lookup"><span data-stu-id="a73ec-129">Remove all spaces between the hexadecimal characters.</span></span> <span data-ttu-id="a73ec-130">完成此操作的一种方法是使用文本编辑器的“查找和替换”功能，将每个空格替换为空字符。</span><span class="sxs-lookup"><span data-stu-id="a73ec-130">One way to accomplish this is to use the text editor's find-and-replace feature and replace each space with a null character.</span></span>  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number"></a><span data-ttu-id="a73ec-131">将 SSL 证书绑定至端口号</span><span class="sxs-lookup"><span data-stu-id="a73ec-131">To bind an SSL certificate to a port number</span></span>  
  
1. <span data-ttu-id="a73ec-132">在 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 或 [!INCLUDE[wxp](../../../../includes/wxp-md.md)] 中，对安全套接字层 (SSL) 存储区使用 HttpCfg.exe 工具的“set”命令将证书绑定至端口号。</span><span class="sxs-lookup"><span data-stu-id="a73ec-132">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool in "set" mode on the Secure Sockets Layer (SSL) store to bind the certificate to a port number.</span></span> <span data-ttu-id="a73ec-133">该工具使用指纹识别证书，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="a73ec-133">The tool uses the thumbprint to identify the certificate, as shown in the following example.</span></span>  
  
    ```  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    -   <span data-ttu-id="a73ec-134">**-I**交换机具有的语法`IP`:`port` ，指示该工具将证书设置为计算机的端口 8012。</span><span class="sxs-lookup"><span data-stu-id="a73ec-134">The **-i** switch has the syntax of `IP`:`port` and instructs the tool to set the certificate to port 8012 of the computer.</span></span> <span data-ttu-id="a73ec-135">另外，也可将端口号前面的四个零替换为计算机的实际 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="a73ec-135">Optionally, the four zeroes that precede the number can also be replaced by the actual IP address of the computer.</span></span>  
  
    -   <span data-ttu-id="a73ec-136">**-H**开关指定证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="a73ec-136">The **-h** switch specifies the thumbprint of the certificate.</span></span>  
  
2. <span data-ttu-id="a73ec-137">在 [!INCLUDE[wv](../../../../includes/wv-md.md)] 中使用 Netsh.exe 工具，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="a73ec-137">In [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}   
    ```  
  
    -   <span data-ttu-id="a73ec-138">**Certhash**参数指定的证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="a73ec-138">The **certhash** parameter specifies the thumbprint of the certificate.</span></span>  
  
    -   <span data-ttu-id="a73ec-139">**Ipport**参数指定的 IP 地址和端口，以及功能类似 **-i**前述 Httpcfg.exe 工具的开关。</span><span class="sxs-lookup"><span data-stu-id="a73ec-139">The **ipport** parameter specifies the IP address and port, and functions just like the **-i** switch of the Httpcfg.exe tool described.</span></span>  
  
    -   <span data-ttu-id="a73ec-140">**Appid**参数是一个 GUID，用于标识所属应用程序。</span><span class="sxs-lookup"><span data-stu-id="a73ec-140">The **appid** parameter is a GUID that can be used to identify the owning application.</span></span>  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a><span data-ttu-id="a73ec-141">将 SSL 证书绑定至端口号并支持客户端证书</span><span class="sxs-lookup"><span data-stu-id="a73ec-141">To bind an SSL certificate to a port number and support client certificates</span></span>  
  
1. <span data-ttu-id="a73ec-142">在 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 或 [!INCLUDE[wxp](../../../../includes/wxp-md.md)] 中，若要支持在传输层使用 X.509 证书进行身份验证的客户端，请按照前面的步骤进行操作，但要向 HttpCfg.exe 另外传递一个命令行参数，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="a73ec-142">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure but pass an additional command-line parameter to HttpCfg.exe, as shown in the following example.</span></span>  
  
    ```  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     <span data-ttu-id="a73ec-143">**-F**开关的语法的`n`其中 n 是介于 1 和 7 之间的数字。</span><span class="sxs-lookup"><span data-stu-id="a73ec-143">The **-f** switch has the syntax of `n` where n is a number between 1 and 7.</span></span> <span data-ttu-id="a73ec-144">值为 2 可在传输层启用客户端证书，如上面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="a73ec-144">A value of 2, as shown in the preceding example, enables client certificates at the transport layer.</span></span> <span data-ttu-id="a73ec-145">值为 3 可启用客户端证书并将这些证书映射至 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="a73ec-145">A value of 3 enables client certificates and maps those certificates to a Windows account.</span></span> <span data-ttu-id="a73ec-146">请参见“HttpCfg.exe 帮助”以获取其他值的行为。</span><span class="sxs-lookup"><span data-stu-id="a73ec-146">See HttpCfg.exe Help for the behavior of other values.</span></span>  
  
2. <span data-ttu-id="a73ec-147">在 [!INCLUDE[wv](../../../../includes/wv-md.md)] 中，若要支持在传输层使用 X.509 证书进行身份验证的客户端，请按照前面的步骤进行操作，但要另外提供一个参数，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="a73ec-147">In [!INCLUDE[wv](../../../../includes/wv-md.md)], to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure, but with an additional parameter, as shown in the following example.</span></span>  
  
    ```  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
### <a name="to-delete-an-ssl-certificate-from-a-port-number"></a><span data-ttu-id="a73ec-148">删除端口号的 SSL 证书</span><span class="sxs-lookup"><span data-stu-id="a73ec-148">To delete an SSL certificate from a port number</span></span>  
  
1. <span data-ttu-id="a73ec-149">使用 HttpCfg.exe 或 Netsh.exe 工具查看计算机上的端口和所有绑定的指纹。</span><span class="sxs-lookup"><span data-stu-id="a73ec-149">Use the HttpCfg.exe or Netsh.exe tool to see the ports and thumbprints of all bindings on the computer.</span></span> <span data-ttu-id="a73ec-150">若要打印到磁盘的信息，请使用重定向字符">"，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="a73ec-150">To print the information to disk, use the redirection character ">", as shown in the following example.</span></span>  
  
    ```  
    httpcfg query ssl>myMachinePorts.txt  
    ```  
  
2. <span data-ttu-id="a73ec-151">在中[!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]或[!INCLUDE[wxp](../../../../includes/wxp-md.md)]，使用 HttpCfg.exe 工具以及**删除**并**ssl**关键字。</span><span class="sxs-lookup"><span data-stu-id="a73ec-151">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool with the **delete** and **ssl** keywords.</span></span> <span data-ttu-id="a73ec-152">使用 **-i**开关指定`IP`:`port`数，并且 **-h**开关指定指纹。</span><span class="sxs-lookup"><span data-stu-id="a73ec-152">Use the **-i** switch to specify the `IP`:`port` number, and the **-h** switch to specify the thumbprint.</span></span>  
  
    ```  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3. <span data-ttu-id="a73ec-153">在 [!INCLUDE[wv](../../../../includes/wv-md.md)] 中使用 Netsh.exe 工具，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="a73ec-153">In [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a><span data-ttu-id="a73ec-154">示例</span><span class="sxs-lookup"><span data-stu-id="a73ec-154">Example</span></span>  
 <span data-ttu-id="a73ec-155">下面的代码演示如何使用 <xref:System.ServiceModel.WSHttpBinding> 类（设置为传输安全）创建自承载服务。</span><span class="sxs-lookup"><span data-stu-id="a73ec-155">The following code shows how to create a self-hosted service using the <xref:System.ServiceModel.WSHttpBinding> class set to transport security.</span></span> <span data-ttu-id="a73ec-156">创建应用程序时，请指定地址中的端口号。</span><span class="sxs-lookup"><span data-stu-id="a73ec-156">When creating an application, specify the port number in the address.</span></span>  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="a73ec-157">请参阅</span><span class="sxs-lookup"><span data-stu-id="a73ec-157">See also</span></span>

- [<span data-ttu-id="a73ec-158">HTTP 传输安全</span><span class="sxs-lookup"><span data-stu-id="a73ec-158">HTTP Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/http-transport-security.md)
