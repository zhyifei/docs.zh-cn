---
title: FindPrivateKey
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 81ca357ccdcbe76f36f3ba56caf2013a80143728
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="findprivatekey"></a><span data-ttu-id="444a0-102">FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="444a0-102">FindPrivateKey</span></span>
<span data-ttu-id="444a0-103">查找与证书存储区中的特定 X.509 证书关联的私钥文件的位置和名称可能很困难。</span><span class="sxs-lookup"><span data-stu-id="444a0-103">It can be difficult to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span> <span data-ttu-id="444a0-104">使用 FindPrivateKey.exe 工具可以更快地完成此过程。</span><span class="sxs-lookup"><span data-stu-id="444a0-104">The FindPrivateKey.exe tool facilitates this process.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="444a0-105">FindPrivateKey 是一个需要在使用之前进行编译的样本。</span><span class="sxs-lookup"><span data-stu-id="444a0-105">FindPrivateKey is a sample that needs to be compiled prior to use.</span></span> <span data-ttu-id="444a0-106">有关如何构建 FindPrivateKey 工具，请参阅"以生成 FindPrivateKey 项目"下面的部分的说明。</span><span class="sxs-lookup"><span data-stu-id="444a0-106">See the "To build the FindPrivateKey project" section below for instructions on how to build the FindPrivateKey tool.</span></span>  
  
 <span data-ttu-id="444a0-107">X.509 证书是由计算机管理员或计算机上的任何用户安装的。</span><span class="sxs-lookup"><span data-stu-id="444a0-107">X.509 certificates are installed by an Administrator or any user in the machine.</span></span> <span data-ttu-id="444a0-108">但是，该证书可以由使用其他帐户（例如 [!INCLUDE[wxp](../../../../includes/wxp-md.md)] 上的 ASPNET 或 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 上的 NETWORK SERVICE 帐户）运行的服务来访问。</span><span class="sxs-lookup"><span data-stu-id="444a0-108">However the certificate may be accessed by a service running under a different account (for example, the ASPNET on [!INCLUDE[wxp](../../../../includes/wxp-md.md)] or the NETWORK SERVICE accounts on [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]).</span></span>  
  
 <span data-ttu-id="444a0-109">此帐户可能没有访问私钥文件的权限，因为证书原来并不是由它安装的。</span><span class="sxs-lookup"><span data-stu-id="444a0-109">This account may not have access to the private key file because the certificate was not installed by it originally.</span></span> <span data-ttu-id="444a0-110">FindPrivateKey 工具可以为您提供给定 X.509 证书的私钥文件的位置。</span><span class="sxs-lookup"><span data-stu-id="444a0-110">The FindPrivateKey tool gives you the location of a given X.509 Certificate's private key file.</span></span> <span data-ttu-id="444a0-111">您可以在知道特定 X.509 证书的私钥文件的位置后立即添加或移除对此文件的权限。</span><span class="sxs-lookup"><span data-stu-id="444a0-111">You can add permissions or remove permissions to this file once you know the location of the particular X.509 certificates' private key file.</span></span>  
  
 <span data-ttu-id="444a0-112">使用证书确保安全性的示例在 Setup.bat 文件中使用 FindPrivateKey 工具。</span><span class="sxs-lookup"><span data-stu-id="444a0-112">The samples that use certificates for security use the FindPrivateKey tool in the Setup.bat file.</span></span> <span data-ttu-id="444a0-113">找到私钥文件后，您可以使用其他工具（如 Cacls.exe）设置该文件的适当访问权限。</span><span class="sxs-lookup"><span data-stu-id="444a0-113">Once the private key file has been found you can use other tools such as Cacls.exe to set the appropriate access rights onto the file.</span></span>  
  
 <span data-ttu-id="444a0-114">使用用户帐户（如自承载可执行文件）运行 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务时，请确保该用户帐户具有该文件的只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="444a0-114">When running a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service under a user account, such as a self-hosted executable, ensure that the user account has read-only access to the file.</span></span> <span data-ttu-id="444a0-115">使用 Internet 信息服务 (IIS) 运行 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务时，该服务使用的默认帐户是 [!INCLUDE[wxp](../../../../includes/wxp-md.md)] 上的 ASPNET 或 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] 上的 NETWORK SERVICE，该帐户默认情况下没有私钥文件的访问权限。</span><span class="sxs-lookup"><span data-stu-id="444a0-115">When running a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service under Internet Information Services (IIS) the default accounts that the service runs under are the ASPNET on [!INCLUDE[wxp](../../../../includes/wxp-md.md)] or the NETWORK SERVICE on [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], which by default do not have access to the private key file.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="444a0-116">示例</span><span class="sxs-lookup"><span data-stu-id="444a0-116">Examples</span></span>  
 <span data-ttu-id="444a0-117">访问进程没有读取特权的证书时，您将看到类似如下示例的异常消息。</span><span class="sxs-lookup"><span data-stu-id="444a0-117">When accessing a certificate for which the process does not have read privilege, you see an exception message similar to the following example.</span></span>  
  
```  
System.ArgumentException was unhandled  
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."  
Source="System.ServiceModel"  
```  
  
 <span data-ttu-id="444a0-118">发生这种情况时，可以使用 FindPrivateKey 工具查找私钥文件，然后为服务正在其中运行的进程设置访问权限。</span><span class="sxs-lookup"><span data-stu-id="444a0-118">When this occurs use the FindPrivateKey tool to find the private key file and then set the access right for the process that the service is running under.</span></span> <span data-ttu-id="444a0-119">例如，可以使用下面示例中所示的 Cacls.exe 工具完成此操作。</span><span class="sxs-lookup"><span data-stu-id="444a0-119">For example, this can be done with the Cacls.exe tool as shown in the following example.</span></span>  
  
```  
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R  
```  
  
#### <a name="to-build-the-findprivatekey-project"></a><span data-ttu-id="444a0-120">生成 FindPrivateKey 项目</span><span class="sxs-lookup"><span data-stu-id="444a0-120">To build the FindPrivateKey project</span></span>  
  
1.  <span data-ttu-id="444a0-121">打开 [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]，然后导航到安装此示例的目录位置下语言特定的子目录。</span><span class="sxs-lookup"><span data-stu-id="444a0-121">Open [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] and navigate to the language-specific subdirectory under the directory location where you installed the sample.</span></span>  
  
2.  <span data-ttu-id="444a0-122">双击 .sln 文件图标，在 Visual Studio 中打开该文件。</span><span class="sxs-lookup"><span data-stu-id="444a0-122">Double-click the .sln file icon to open the file in Visual Studio.</span></span>  
  
3.  <span data-ttu-id="444a0-123">在**生成**菜单上，选择**重新生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="444a0-123">In the **Build** menu, select **Rebuild Solution**.</span></span> <span data-ttu-id="444a0-124">客户端程序文件在 client\bin 中生成，服务程序文件在 service\bin 中生成。</span><span class="sxs-lookup"><span data-stu-id="444a0-124">The client program files are built to client\bin and the service program files are built to service\bin.</span></span>  
  
4.  <span data-ttu-id="444a0-125">生成解决方案将生成如下文件：FindPrivateKey.exe。</span><span class="sxs-lookup"><span data-stu-id="444a0-125">Building the solution generates the file: FindPrivateKey.exe.</span></span>  
  
## <a name="conventionscommand-line-entries"></a><span data-ttu-id="444a0-126">约定 - 命令行条目</span><span class="sxs-lookup"><span data-stu-id="444a0-126">Conventions—Command-Line Entries</span></span>  
 <span data-ttu-id="444a0-127">"[*选项*]"表示一组可选的参数。</span><span class="sxs-lookup"><span data-stu-id="444a0-127">"[*option*]" represents an optional set of parameters.</span></span>  
  
 <span data-ttu-id="444a0-128">"{*选项*}"代表一组强制参数。</span><span class="sxs-lookup"><span data-stu-id="444a0-128">"{*option*}" represents a mandatory set of parameters.</span></span>  
  
 <span data-ttu-id="444a0-129">"*选项 1* &#124;*选项 2*"代表一种选择的选项集之间。</span><span class="sxs-lookup"><span data-stu-id="444a0-129">"*option1* &#124; *option2*" represents a choice between sets of options.</span></span>  
  
 <span data-ttu-id="444a0-130">"\<*值*>"代表要输入的参数值。</span><span class="sxs-lookup"><span data-stu-id="444a0-130">"\<*value*>" represents a parameter value to be entered.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="444a0-131">用法</span><span class="sxs-lookup"><span data-stu-id="444a0-131">Usage</span></span>  
  
```  
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]  
```  
  
 <span data-ttu-id="444a0-132">其中：</span><span class="sxs-lookup"><span data-stu-id="444a0-132">Where:</span></span>  
  
```  
       <subjectName> The subject name of the certificate  
       <thumbprint>  The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)  
       -f            output file name only  
       -d            output directory only  
       -a            output absolute file name  
```  
  
 <span data-ttu-id="444a0-133">如果没在命令提示符中指定任何参数，将显示此帮助文本。</span><span class="sxs-lookup"><span data-stu-id="444a0-133">If no parameters are specified at the command prompt then this help text is displayed.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="444a0-134">示例</span><span class="sxs-lookup"><span data-stu-id="444a0-134">Examples</span></span>  
 <span data-ttu-id="444a0-135">此示例在 Current User.FindPrivateKey My CurrentUser -n "CN=localhost" 的“个人”存储区中查找主题名称为 "CN=localhost" 的证书的文件名。</span><span class="sxs-lookup"><span data-stu-id="444a0-135">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User.FindPrivateKey My CurrentUser -n "CN=localhost".</span></span>  
  
 <span data-ttu-id="444a0-136">此示例在 Current 的“个人”存储区中查找主题名称为 "CN=localhost" 的证书的文件名，并输出完整的目录路径。</span><span class="sxs-lookup"><span data-stu-id="444a0-136">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current and output the full directory path.</span></span>  
  
```  
User.FindPrivateKey My CurrentUser -n "CN=localhost" -a  
```  
  
 <span data-ttu-id="444a0-137">此示例在“本地计算机”的“个人”存储区中查找指纹为 "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" 的证书的文件名。</span><span class="sxs-lookup"><span data-stu-id="444a0-137">This example finds the filename of the certificate with a thumbprint of "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", in the Personal store of the Local Computer.</span></span>  
  
```  
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –c  
```  
  
## <a name="see-also"></a><span data-ttu-id="444a0-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="444a0-138">See Also</span></span>
