---
title: "Internet Information Services (IIS) 服务器证书安装说明"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 11281490-d2ac-4324-8f33-e7714611a34b
caps.latest.revision: "18"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 4b9496d471ca262e640c927619ccea8e4b4f4145
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="internet-information-services-iis-server-certificate-installation-instructions"></a><span data-ttu-id="59621-102">Internet Information Services (IIS) 服务器证书安装说明</span><span class="sxs-lookup"><span data-stu-id="59621-102">Internet Information Services (IIS) Server Certificate Installation Instructions</span></span>
<span data-ttu-id="59621-103">若要运行可与 Internet 信息服务 (IIS) 安全通信的示例，您必须创建和安装服务器证书。</span><span class="sxs-lookup"><span data-stu-id="59621-103">To run the samples that securely communicate with Internet Information Services (IIS), you must create and install a server certificate.</span></span>  
  
## <a name="step-1-creating-certificates"></a><span data-ttu-id="59621-104">步骤 1。</span><span class="sxs-lookup"><span data-stu-id="59621-104">Step 1.</span></span> <span data-ttu-id="59621-105">创建证书</span><span class="sxs-lookup"><span data-stu-id="59621-105">Creating Certificates</span></span>  
 <span data-ttu-id="59621-106">若要为计算机创建证书，请使用管理员特权打开 Visual Studio 命令提示，并运行包含在使用带 IIS 的安全通信的每个示例中的 Setup.bat。</span><span class="sxs-lookup"><span data-stu-id="59621-106">To create a certificate for your computer, open a Visual Studio command prompt with administrator privileges and run the Setup.bat that is included in each of the samples that use secure communication with IIS.</span></span> <span data-ttu-id="59621-107">在运行此批处理文件之前，确保路径包括其中包含 Makecert.exe 的文件夹。</span><span class="sxs-lookup"><span data-stu-id="59621-107">Ensure that the path includes the folder that contains Makecert.exe before you run this batch file.</span></span> <span data-ttu-id="59621-108">以下命令用于在 Setup.bat 中创建证书。</span><span class="sxs-lookup"><span data-stu-id="59621-108">The following command is used to create the certificate in Setup.bat.</span></span>  
  
```  
makecert -sr LocalMachine -ss My -n CN=ServiceModelSamples-HTTPS-Server -sky exchange -sk ServiceModelSamples-HTTPS-Key  
```  
  
## <a name="step-2-installing-certificates"></a><span data-ttu-id="59621-109">步骤 2。</span><span class="sxs-lookup"><span data-stu-id="59621-109">Step 2.</span></span> <span data-ttu-id="59621-110">安装证书</span><span class="sxs-lookup"><span data-stu-id="59621-110">Installing Certificates</span></span>  
 <span data-ttu-id="59621-111">安装刚刚创建的证书所需执行的步骤取决于您所使用的 IIS 版本。</span><span class="sxs-lookup"><span data-stu-id="59621-111">The steps required to install the certificates you just created depend on which version of IIS you are using.</span></span>  
  
#### <a name="to-install-iis-on-iis-51-windows-xp-and-iis-60-windows-server-2003"></a><span data-ttu-id="59621-112">在 IIS 5.1 (Windows XP) 和 IIS 6.0 (Windows Server 2003) 上安装 IIS</span><span class="sxs-lookup"><span data-stu-id="59621-112">To install IIS on IIS 5.1 (Windows XP) and IIS 6.0 (Windows Server 2003)</span></span>  
  
1.  <span data-ttu-id="59621-113">打开 Internet 信息服务管理器 MMC 管理单元。</span><span class="sxs-lookup"><span data-stu-id="59621-113">Open the Internet Information Services Manager MMC Snap-In.</span></span>  
  
2.  <span data-ttu-id="59621-114">右击默认网站并选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="59621-114">Right-click the default Web site and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="59621-115">选择**目录安全性**选项卡。</span><span class="sxs-lookup"><span data-stu-id="59621-115">Select the **Directory Security** tab.</span></span>  
  
4.  <span data-ttu-id="59621-116">单击**服务器证书**按钮。</span><span class="sxs-lookup"><span data-stu-id="59621-116">Click the **Server Certificate** button.</span></span> <span data-ttu-id="59621-117">Web 服务器证书向导将启动。</span><span class="sxs-lookup"><span data-stu-id="59621-117">The Web Server Certificate Wizard starts.</span></span>  
  
5.  <span data-ttu-id="59621-118">完成该向导。</span><span class="sxs-lookup"><span data-stu-id="59621-118">Complete the wizard.</span></span> <span data-ttu-id="59621-119">选择用于分配证书的选项。</span><span class="sxs-lookup"><span data-stu-id="59621-119">Select the option to assign a certificate.</span></span> <span data-ttu-id="59621-120">从显示的证书列表中选择 ServiceModelSamples-HTTPS-Server 证书。</span><span class="sxs-lookup"><span data-stu-id="59621-120">Select the ServiceModelSamples-HTTPS-Server certificate from the list of certificates that are displayed.</span></span>  
  
     <span data-ttu-id="59621-121">![IIS 证书向导](../../../../docs/framework/wcf/samples/media/iiscertificate-wizard.GIF "IISCertificate_Wizard")</span><span class="sxs-lookup"><span data-stu-id="59621-121">![IIS Certificate Wizard](../../../../docs/framework/wcf/samples/media/iiscertificate-wizard.GIF "IISCertificate_Wizard")</span></span>  
  
6.  <span data-ttu-id="59621-122">通过使用 HTTPS 地址 https://localhost/servicemodelsamples/service.svc，在浏览器中测试对服务的访问。</span><span class="sxs-lookup"><span data-stu-id="59621-122">Test access to the service in a browser by using the HTTPS address https://localhost/servicemodelsamples/service.svc.</span></span>  
  
#### <a name="if-ssl-was-previously-configured-by-using-httpcfgexe"></a><span data-ttu-id="59621-123">如果以前使用 Httpcfg.exe 配置了 SSL</span><span class="sxs-lookup"><span data-stu-id="59621-123">If SSL was previously configured by using Httpcfg.exe</span></span>  
  
1.  <span data-ttu-id="59621-124">使用 Makecert.exe（或运行 Setup.bat）创建服务器证书。</span><span class="sxs-lookup"><span data-stu-id="59621-124">Use Makecert.exe (or run Setup.bat) to create the server certificate.</span></span>  
  
2.  <span data-ttu-id="59621-125">按照前面的步骤运行 IIS 管理器并安装证书。</span><span class="sxs-lookup"><span data-stu-id="59621-125">Run the IIS manager and install the certificate according to the previous steps.</span></span>  
  
3.  <span data-ttu-id="59621-126">将以下代码行添加到客户端程序。</span><span class="sxs-lookup"><span data-stu-id="59621-126">Add the following line of code to the client program.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="59621-127">只有测试证书（比如通过 Makecert.exe 创建的那些证书）才需要此代码。</span><span class="sxs-lookup"><span data-stu-id="59621-127">This code is only required for test certificates such as those created by Makecert.exe.</span></span> <span data-ttu-id="59621-128">建议不要为成品代码执行此操作。</span><span class="sxs-lookup"><span data-stu-id="59621-128">It is not recommended for production code.</span></span>  
  
```  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```  
  
#### <a name="to-install-iis-on-iis-70-windows-vista-and-windows-server-2008"></a><span data-ttu-id="59621-129">在 IIS 7.0（Windows Vista 和 Windows Server 2008）上安装 IIS</span><span class="sxs-lookup"><span data-stu-id="59621-129">To install IIS on IIS 7.0 (Windows Vista and Windows Server 2008)</span></span>  
  
1.  <span data-ttu-id="59621-130">从**启动**菜单上，单击**运行**，然后键入**inetmgr**若要打开 Internet 信息服务 (IIS) MMC 管理单元。</span><span class="sxs-lookup"><span data-stu-id="59621-130">From the **Start** menu, click **Run**, then type **inetmgr** to open the Internet Information Services (IIS) MMC snap-in.</span></span>  
  
2.  <span data-ttu-id="59621-131">右键单击**Default Web Site**和选择**编辑绑定...**</span><span class="sxs-lookup"><span data-stu-id="59621-131">Right-click the **Default Web Site** and select **Edit Bindings…**</span></span>  
  
3.  <span data-ttu-id="59621-132">单击**添加**按钮**站点绑定**对话框。</span><span class="sxs-lookup"><span data-stu-id="59621-132">Click the **Add** button of the **Site Bindings** dialog box.</span></span>  
  
4.  <span data-ttu-id="59621-133">选择**HTTPS**从**类型**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="59621-133">Select **HTTPS** from the **Type** drop-down list.</span></span>  
  
5.  <span data-ttu-id="59621-134">选择**ServiceModelSamples HTTPS 服务器**从**SSL 证书**下拉列表，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="59621-134">Select the **ServiceModelSamples-HTTPS-Server** from the **SSL certificate** drop-down list and click **OK**.</span></span>  
  
6.  <span data-ttu-id="59621-135">通过使用 HTTPS 地址 https://localhost/servicemodelsamples/service.svc，在浏览器中测试对服务的访问。</span><span class="sxs-lookup"><span data-stu-id="59621-135">Test access to the service in a browser by using the HTTPS address https://localhost/servicemodelsamples/service.svc.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="59621-136">由于刚刚安装的测试证书不是受信任的证书，因此，在浏览用此证书保护的本地 Web 地址时，您可能会遇到其他 Internet Explorer 安全警告。</span><span class="sxs-lookup"><span data-stu-id="59621-136">Because the test certificate you have just installed is not a trusted certificate, you may encounter additional Internet Explorer security warnings when browsing to local Web addresses secured with this certificate.</span></span>  
  
## <a name="removing-certificates"></a><span data-ttu-id="59621-137">移除证书</span><span class="sxs-lookup"><span data-stu-id="59621-137">Removing Certificates</span></span>  
  
-   <span data-ttu-id="59621-138">按照前面的指引使用 Internet Information Services 管理器，但要移除（而不是添加）证书或绑定。</span><span class="sxs-lookup"><span data-stu-id="59621-138">Use the Internet Information Services Manager as previously directed, but remove the certificate or binding instead of adding it.</span></span>  
  
-   <span data-ttu-id="59621-139">使用以下命令移除计算机证书。</span><span class="sxs-lookup"><span data-stu-id="59621-139">Remove the computer certificate by using the following command.</span></span>  
  
    ```  
    httpcfg delete ssl -i 0.0.0.0:443  
    ```
