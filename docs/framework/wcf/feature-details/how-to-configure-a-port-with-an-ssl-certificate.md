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
ms.openlocfilehash: 90d5424e12bb770dc3da85e1b2738206f4777c0c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185112"
---
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a><span data-ttu-id="550ae-102">如何：使用 SSL 证书配置端口</span><span class="sxs-lookup"><span data-stu-id="550ae-102">How to: Configure a Port with an SSL Certificate</span></span>

<span data-ttu-id="550ae-103">使用使用传输安全性<xref:System.ServiceModel.WSHttpBinding>的类创建自托管的 Windows 通信基础 （WCF） 服务时，还必须配置具有 X.509 证书的端口。</span><span class="sxs-lookup"><span data-stu-id="550ae-103">When creating a self-hosted Windows Communication Foundation (WCF) service with the <xref:System.ServiceModel.WSHttpBinding> class that uses transport security, you must also configure a port with an X.509 certificate.</span></span> <span data-ttu-id="550ae-104">如果不是在创建自承载服务，可以在 Internet 信息服务 (IIS) 上承载服务。</span><span class="sxs-lookup"><span data-stu-id="550ae-104">If you are not creating a self-hosted service, you can host your service on Internet Information Services (IIS).</span></span> <span data-ttu-id="550ae-105">有关详细信息，请参阅[HTTP 传输安全](../../../../docs/framework/wcf/feature-details/http-transport-security.md)。</span><span class="sxs-lookup"><span data-stu-id="550ae-105">For more information, see [HTTP Transport Security](../../../../docs/framework/wcf/feature-details/http-transport-security.md).</span></span>  
  
 <span data-ttu-id="550ae-106">若要配置端口，使用的工具取决于计算机运行的操作系统。</span><span class="sxs-lookup"><span data-stu-id="550ae-106">To configure a port, the tool you use depends on the operating system that is running on your machine.</span></span>  
  
 <span data-ttu-id="550ae-107">如果您正在运行 Windows Server 2003，请使用 HttpCfg.exe 工具。</span><span class="sxs-lookup"><span data-stu-id="550ae-107">If you are running Windows Server 2003, use the HttpCfg.exe tool.</span></span> <span data-ttu-id="550ae-108">在 Windows 服务器 2003 上，将安装此工具。</span><span class="sxs-lookup"><span data-stu-id="550ae-108">On Windows Server 2003, this tool is installed.</span></span> <span data-ttu-id="550ae-109">有关详细信息，请参阅[Httpcfg 概述](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc787508(v=ws.10))。</span><span class="sxs-lookup"><span data-stu-id="550ae-109">For more information, see [Httpcfg Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc787508(v=ws.10)).</span></span> <span data-ttu-id="550ae-110">[Windows 支持工具文档](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc781601(v=ws.10))解释了 Httpcfg.exe 工具的语法。</span><span class="sxs-lookup"><span data-stu-id="550ae-110">The [Windows Support Tools documentation](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc781601(v=ws.10)) explains the syntax for the Httpcfg.exe tool.</span></span>  
  
 <span data-ttu-id="550ae-111">如果您正在运行 Windows Vista，请使用已安装的 Netsh.exe 工具。</span><span class="sxs-lookup"><span data-stu-id="550ae-111">If you are running Windows Vista, use the Netsh.exe tool that is already installed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="550ae-112">修改存储在计算机上的证书需要管理权限。</span><span class="sxs-lookup"><span data-stu-id="550ae-112">Modifying certificates stored on the computer requires administrative privileges.</span></span>  
  
## <a name="determine-how-ports-are-configured"></a><span data-ttu-id="550ae-113">确定端口的配置方式</span><span class="sxs-lookup"><span data-stu-id="550ae-113">Determine how ports are configured</span></span>  
  
1. <span data-ttu-id="550ae-114">在 Windows 服务器 2003 或 Windows XP 中，使用 HttpCfg.exe 工具使用**查询**和**ssl**开关查看当前端口配置，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="550ae-114">In Windows Server 2003 or Windows XP, use the HttpCfg.exe tool to view the current port configuration, using the **query** and **ssl** switches, as shown in the following example.</span></span>  
  
    ```console
    httpcfg query ssl  
    ```  
  
2. <span data-ttu-id="550ae-115">在 Windows Vista 中，使用 Netsh.exe 工具查看当前端口配置，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="550ae-115">In Windows Vista, use the Netsh.exe tool to view the current port configuration, as shown in the following example.</span></span>  
  
    ```console  
    netsh http show sslcert  
    ```  
  
## <a name="get-a-certificates-thumbprint"></a><span data-ttu-id="550ae-116">获取证书的指纹</span><span class="sxs-lookup"><span data-stu-id="550ae-116">Get a certificate's thumbprint</span></span>  
  
1. <span data-ttu-id="550ae-117">使用证书 MMC 管理单元查找用于客户端身份验证的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="550ae-117">Use the Certificates MMC snap-in to find an X.509 certificate that has an intended purpose of client authentication.</span></span> <span data-ttu-id="550ae-118">有关详细信息，请参阅[如何：使用 MMC 管理单元查看证书](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md)。</span><span class="sxs-lookup"><span data-stu-id="550ae-118">For more information, see [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
2. <span data-ttu-id="550ae-119">访问证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="550ae-119">Access the certificate's thumbprint.</span></span> <span data-ttu-id="550ae-120">有关详细信息，请参阅[如何：检索证书的指纹](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md)。</span><span class="sxs-lookup"><span data-stu-id="550ae-120">For more information, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
3. <span data-ttu-id="550ae-121">将证书指纹复制到文本编辑器，如 Notepad。</span><span class="sxs-lookup"><span data-stu-id="550ae-121">Copy the thumbprint of the certificate into a text editor, such as Notepad.</span></span>  
  
4. <span data-ttu-id="550ae-122">移除十六进制字符之间的所有空格。</span><span class="sxs-lookup"><span data-stu-id="550ae-122">Remove all spaces between the hexadecimal characters.</span></span> <span data-ttu-id="550ae-123">完成此操作的一种方法是使用文本编辑器的“查找和替换”功能，将每个空格替换为空字符。</span><span class="sxs-lookup"><span data-stu-id="550ae-123">One way to accomplish this is to use the text editor's find-and-replace feature and replace each space with a null character.</span></span>  
  
## <a name="bind-an-ssl-certificate-to-a-port-number"></a><span data-ttu-id="550ae-124">将 SSL 证书绑定到端口号</span><span class="sxs-lookup"><span data-stu-id="550ae-124">Bind an SSL certificate to a port number</span></span>  
  
1. <span data-ttu-id="550ae-125">在 Windows 服务器 2003 或 Windows XP 中，在安全套接字层 （SSL） 存储的"设置"模式下使用 HttpCfg.exe 工具将证书绑定到端口号。</span><span class="sxs-lookup"><span data-stu-id="550ae-125">In Windows Server 2003 or Windows XP, use the HttpCfg.exe tool in "set" mode on the Secure Sockets Layer (SSL) store to bind the certificate to a port number.</span></span> <span data-ttu-id="550ae-126">该工具使用指纹识别证书，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="550ae-126">The tool uses the thumbprint to identify the certificate, as shown in the following example.</span></span>  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    - <span data-ttu-id="550ae-127">**-i**开关的语法为`IP`：`port`并指示工具将证书设置为计算机的端口 8012。</span><span class="sxs-lookup"><span data-stu-id="550ae-127">The **-i** switch has the syntax of `IP`:`port` and instructs the tool to set the certificate to port 8012 of the computer.</span></span> <span data-ttu-id="550ae-128">另外，也可将端口号前面的四个零替换为计算机的实际 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="550ae-128">Optionally, the four zeroes that precede the number can also be replaced by the actual IP address of the computer.</span></span>  
  
    - <span data-ttu-id="550ae-129">**-h**开关指定证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="550ae-129">The **-h** switch specifies the thumbprint of the certificate.</span></span>  
  
2. <span data-ttu-id="550ae-130">在 Windows Vista 中，请使用 Netsh.exe 工具，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="550ae-130">In Windows Vista, use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}
    ```  
  
    - <span data-ttu-id="550ae-131">**证书**参数指定证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="550ae-131">The **certhash** parameter specifies the thumbprint of the certificate.</span></span>  
  
    - <span data-ttu-id="550ae-132">**ipport**参数指定 IP 地址和端口，其功能与描述的 Httpcfg.exe 工具的 **-i**开关类似。</span><span class="sxs-lookup"><span data-stu-id="550ae-132">The **ipport** parameter specifies the IP address and port, and functions just like the **-i** switch of the Httpcfg.exe tool described.</span></span>  
  
    - <span data-ttu-id="550ae-133">**appid**参数是一个 GUID，可用于标识所属应用程序。</span><span class="sxs-lookup"><span data-stu-id="550ae-133">The **appid** parameter is a GUID that can be used to identify the owning application.</span></span>  
  
## <a name="bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a><span data-ttu-id="550ae-134">将 SSL 证书绑定到端口号并支持客户端证书</span><span class="sxs-lookup"><span data-stu-id="550ae-134">Bind an SSL certificate to a port number and support client certificates</span></span>  
  
1. <span data-ttu-id="550ae-135">在 Windows Server 2003 或 Windows XP 中，为了支持在传输层使用 X.509 证书进行身份验证的客户端，请按照上述过程操作，但将附加命令行参数传递给 HttpCfg.exe，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="550ae-135">In Windows Server 2003 or Windows XP, to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure but pass an additional command-line parameter to HttpCfg.exe, as shown in the following example.</span></span>  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     <span data-ttu-id="550ae-136">**-f**开关的语法`n`是 n 是介于 1 和 7 之间的数字。</span><span class="sxs-lookup"><span data-stu-id="550ae-136">The **-f** switch has the syntax of `n` where n is a number between 1 and 7.</span></span> <span data-ttu-id="550ae-137">值为 2 可在传输层启用客户端证书，如上面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="550ae-137">A value of 2, as shown in the preceding example, enables client certificates at the transport layer.</span></span> <span data-ttu-id="550ae-138">值为 3 可启用客户端证书并将这些证书映射至 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="550ae-138">A value of 3 enables client certificates and maps those certificates to a Windows account.</span></span> <span data-ttu-id="550ae-139">请参见“HttpCfg.exe 帮助”以获取其他值的行为。</span><span class="sxs-lookup"><span data-stu-id="550ae-139">See HttpCfg.exe Help for the behavior of other values.</span></span>  
  
2. <span data-ttu-id="550ae-140">在 Windows Vista 中，为了支持在传输层使用 X.509 证书进行身份验证的客户端，请遵循前面的过程，但使用附加参数，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="550ae-140">In Windows Vista, to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure, but with an additional parameter, as shown in the following example.</span></span>  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
## <a name="delete-an-ssl-certificate-from-a-port-number"></a><span data-ttu-id="550ae-141">从端口号中删除 SSL 证书</span><span class="sxs-lookup"><span data-stu-id="550ae-141">Delete an SSL certificate from a port number</span></span>  
  
1. <span data-ttu-id="550ae-142">使用 HttpCfg.exe 或 Netsh.exe 工具查看计算机上的端口和所有绑定的指纹。</span><span class="sxs-lookup"><span data-stu-id="550ae-142">Use the HttpCfg.exe or Netsh.exe tool to see the ports and thumbprints of all bindings on the computer.</span></span> <span data-ttu-id="550ae-143">要将信息打印到磁盘，请使用重定向字符">"，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="550ae-143">To print the information to disk, use the redirection character ">", as shown in the following example.</span></span>  
  
    ```console  
    httpcfg query ssl>myMachinePorts.txt  
    ```
  
2. <span data-ttu-id="550ae-144">在 Windows 服务器 2003 或 Windows XP 中，使用 HttpCfg.exe 工具**删除和\*\*\*\*ssl**关键字。</span><span class="sxs-lookup"><span data-stu-id="550ae-144">In Windows Server 2003 or Windows XP, use the HttpCfg.exe tool with the **delete** and **ssl** keywords.</span></span> <span data-ttu-id="550ae-145">使用 **-i**开关指定`IP`：`port`编号和 **-h**开关来指定指纹。</span><span class="sxs-lookup"><span data-stu-id="550ae-145">Use the **-i** switch to specify the `IP`:`port` number, and the **-h** switch to specify the thumbprint.</span></span>  
  
    ```console  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3. <span data-ttu-id="550ae-146">在 Windows Vista 中，请使用 Netsh.exe 工具，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="550ae-146">In Windows Vista, use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```console  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a><span data-ttu-id="550ae-147">示例</span><span class="sxs-lookup"><span data-stu-id="550ae-147">Example</span></span>  

 <span data-ttu-id="550ae-148">下面的代码演示如何使用 <xref:System.ServiceModel.WSHttpBinding> 类（设置为传输安全）创建自承载服务。</span><span class="sxs-lookup"><span data-stu-id="550ae-148">The following code shows how to create a self-hosted service using the <xref:System.ServiceModel.WSHttpBinding> class set to transport security.</span></span> <span data-ttu-id="550ae-149">创建应用程序时，请指定地址中的端口号。</span><span class="sxs-lookup"><span data-stu-id="550ae-149">When creating an application, specify the port number in the address.</span></span>  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="550ae-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="550ae-150">See also</span></span>

- [<span data-ttu-id="550ae-151">HTTP 传输安全性</span><span class="sxs-lookup"><span data-stu-id="550ae-151">HTTP Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/http-transport-security.md)
