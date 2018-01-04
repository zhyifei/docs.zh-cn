---
title: "FindPrivateKey 示例-WCF"
ms.date: 12/04/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords: FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 32e1a4a3de01371d67be8d19613b1f29c1ce3c29
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="findprivatekey-sample"></a><span data-ttu-id="e56c4-102">FindPrivateKey 示例</span><span class="sxs-lookup"><span data-stu-id="e56c4-102">FindPrivateKey sample</span></span>

<span data-ttu-id="e56c4-103">查找与证书存储区中的特定 X.509 证书关联的私钥文件的位置和名称可能很困难。</span><span class="sxs-lookup"><span data-stu-id="e56c4-103">It can be difficult to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span> <span data-ttu-id="e56c4-104">使用 FindPrivateKey.exe 工具可以更快地完成此过程。</span><span class="sxs-lookup"><span data-stu-id="e56c4-104">The FindPrivateKey.exe tool facilitates this process.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e56c4-105">FindPrivateKey 是一个需要在使用之前进行编译的样本。</span><span class="sxs-lookup"><span data-stu-id="e56c4-105">FindPrivateKey is a sample that needs to be compiled prior to use.</span></span> <span data-ttu-id="e56c4-106">请参阅[以生成 FindPrivateKey 项目](#to-build-the-findprivatekey-project)一部分以获取有关如何构建 FindPrivateKey 工具的说明。</span><span class="sxs-lookup"><span data-stu-id="e56c4-106">See the [To build the FindPrivateKey project](#to-build-the-findprivatekey-project) section for instructions on how to build the FindPrivateKey tool.</span></span>

<span data-ttu-id="e56c4-107">X.509 证书是由计算机管理员或计算机上的任何用户安装的。</span><span class="sxs-lookup"><span data-stu-id="e56c4-107">X.509 certificates are installed by an Administrator or any user in the machine.</span></span> <span data-ttu-id="e56c4-108">但是，该证书可能在不同帐户下运行的服务可访问。</span><span class="sxs-lookup"><span data-stu-id="e56c4-108">However, the certificate may be accessed by a service running under a different account.</span></span> <span data-ttu-id="e56c4-109">例如，NETWORK SERVICE 帐户。</span><span class="sxs-lookup"><span data-stu-id="e56c4-109">For example, the NETWORK SERVICE account.</span></span>

<span data-ttu-id="e56c4-110">此帐户可能没有访问私钥文件的权限，因为证书原来并不是由它安装的。</span><span class="sxs-lookup"><span data-stu-id="e56c4-110">This account may not have access to the private key file because the certificate was not installed by it originally.</span></span> <span data-ttu-id="e56c4-111">FindPrivateKey 工具可以为您提供给定 X.509 证书的私钥文件的位置。</span><span class="sxs-lookup"><span data-stu-id="e56c4-111">The FindPrivateKey tool gives you the location of a given X.509 Certificate's private key file.</span></span> <span data-ttu-id="e56c4-112">您可以在知道特定 X.509 证书的私钥文件的位置后立即添加或移除对此文件的权限。</span><span class="sxs-lookup"><span data-stu-id="e56c4-112">You can add permissions or remove permissions to this file once you know the location of the particular X.509 certificates' private key file.</span></span>

<span data-ttu-id="e56c4-113">使用证书来获得安全的示例使用中的 FindPrivateKey 工具*Setup.bat*文件。</span><span class="sxs-lookup"><span data-stu-id="e56c4-113">The samples that use certificates for security use the FindPrivateKey tool in the *Setup.bat* file.</span></span> <span data-ttu-id="e56c4-114">找到私钥文件后你可以使用其他工具如*Cacls.exe*设置文件的适当访问权限。</span><span class="sxs-lookup"><span data-stu-id="e56c4-114">Once the private key file has been found, you can use other tools such as *Cacls.exe* to set the appropriate access rights onto the file.</span></span>

<span data-ttu-id="e56c4-115">在运行 Windows Communication Foundation (WCF) 服务的用户帐户，如自承载的可执行文件，确保用户帐户时请对文件具有只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="e56c4-115">When running a Windows Communication Foundation (WCF) service under a user account, such as a self-hosted executable, ensure that the user account has read-only access to the file.</span></span> <span data-ttu-id="e56c4-116">运行 WCF 服务在 Internet 信息服务 (IIS) 时运行该服务的默认帐户将是网络服务在 IIS 7 和早期版本中或在 IIS 7.5 和更高版本上的应用程序池标识。</span><span class="sxs-lookup"><span data-stu-id="e56c4-116">When running a WCF service under Internet Information Services (IIS) the default accounts that the service runs under are the NETWORK SERVICE on IIS 7 and earlier versions, or Application Pool Identity on IIS 7.5 and later versions.</span></span> <span data-ttu-id="e56c4-117">有关详细信息，请参阅[应用程序池标识](/iis/manage/configuring-security/application-pool-identities)。</span><span class="sxs-lookup"><span data-stu-id="e56c4-117">For more information, see [Application Pool Identities](/iis/manage/configuring-security/application-pool-identities).</span></span>

## <a name="examples"></a><span data-ttu-id="e56c4-118">示例</span><span class="sxs-lookup"><span data-stu-id="e56c4-118">Examples</span></span>

<span data-ttu-id="e56c4-119">访问时为其进程不具有读取的权限的证书，你将看到类似于下面的示例的异常消息：</span><span class="sxs-lookup"><span data-stu-id="e56c4-119">When accessing a certificate for which the process doesn't have read privilege, you see an exception message similar to the following example:</span></span>

```
System.ArgumentException was unhandled
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."
Source="System.ServiceModel"
```

<span data-ttu-id="e56c4-120">当发生这种情况时，使用 FindPrivateKey 工具查找私钥文件，并将访问权限的进程的服务下运行。</span><span class="sxs-lookup"><span data-stu-id="e56c4-120">When this occurs, use the FindPrivateKey tool to find the private key file, and then set the access right for the process that the service is running under.</span></span> <span data-ttu-id="e56c4-121">例如，这可以通过实现的 Cacls.exe 工具中下面的示例所示：</span><span class="sxs-lookup"><span data-stu-id="e56c4-121">For example, this can be done with the Cacls.exe tool as shown in the following example:</span></span>

```
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R
```

#### <a name="to-build-the-findprivatekey-project"></a><span data-ttu-id="e56c4-122">生成 FindPrivateKey 项目</span><span class="sxs-lookup"><span data-stu-id="e56c4-122">To build the FindPrivateKey project</span></span>

<span data-ttu-id="e56c4-123">若要下载的项目，请访问[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://www.microsoft.com/download/details.aspx?id=21459)。</span><span class="sxs-lookup"><span data-stu-id="e56c4-123">To download the project, visit [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).</span></span>

1. <span data-ttu-id="e56c4-124">打开[!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]并导航到*WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS*安装示例的位置的目录位置下的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e56c4-124">Open [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] and navigate to the *WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS* folder under the directory location where you installed the sample.</span></span>

2. <span data-ttu-id="e56c4-125">双击 .sln 文件图标，在 Visual Studio 中打开该文件。</span><span class="sxs-lookup"><span data-stu-id="e56c4-125">Double-click the .sln file icon to open the file in Visual Studio.</span></span>

3. <span data-ttu-id="e56c4-126">在**生成**菜单上，选择**重新生成解决方案**。</span><span class="sxs-lookup"><span data-stu-id="e56c4-126">In the **Build** menu, select **Rebuild Solution**.</span></span>

4. <span data-ttu-id="e56c4-127">生成解决方案将生成如下文件：FindPrivateKey.exe。</span><span class="sxs-lookup"><span data-stu-id="e56c4-127">Building the solution generates the file: FindPrivateKey.exe.</span></span>

## <a name="conventionscommand-line-entries"></a><span data-ttu-id="e56c4-128">约定-命令行条目</span><span class="sxs-lookup"><span data-stu-id="e56c4-128">Conventions—Command-Line entries</span></span>

 <span data-ttu-id="e56c4-129">"[*选项*]"表示一组可选的参数。</span><span class="sxs-lookup"><span data-stu-id="e56c4-129">"[*option*]" represents an optional set of parameters.</span></span>

 <span data-ttu-id="e56c4-130">"{*选项*}"代表一组强制参数。</span><span class="sxs-lookup"><span data-stu-id="e56c4-130">"{*option*}" represents a mandatory set of parameters.</span></span>

 <span data-ttu-id="e56c4-131">"*选项 1* &#124;*选项 2*"代表一种选择的选项集之间。</span><span class="sxs-lookup"><span data-stu-id="e56c4-131">"*option1* &#124; *option2*" represents a choice between sets of options.</span></span>

 <span data-ttu-id="e56c4-132">"\<*值*>"代表要输入的参数值。</span><span class="sxs-lookup"><span data-stu-id="e56c4-132">"\<*value*>" represents a parameter value to be entered.</span></span>

## <a name="usage"></a><span data-ttu-id="e56c4-133">用法</span><span class="sxs-lookup"><span data-stu-id="e56c4-133">Usage</span></span>

```
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

<span data-ttu-id="e56c4-134">其中：</span><span class="sxs-lookup"><span data-stu-id="e56c4-134">Where:</span></span>

```
       <subjectName> The subject name of the certificate
       <thumbprint>  The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)
       -f            output file name only
       -d            output directory only
       -a            output absolute file name
```

<span data-ttu-id="e56c4-135">如果未指定参数在命令提示符下，将显示此帮助文本。</span><span class="sxs-lookup"><span data-stu-id="e56c4-135">If no parameters are specified at the command prompt, then this help text is displayed.</span></span>

## <a name="examples"></a><span data-ttu-id="e56c4-136">示例</span><span class="sxs-lookup"><span data-stu-id="e56c4-136">Examples</span></span>

<span data-ttu-id="e56c4-137">本示例查找的文件名的证书的主题名称为"CN = localhost"，当前用户的个人存储中。</span><span class="sxs-lookup"><span data-stu-id="e56c4-137">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User.</span></span>

```
FindPrivateKey My CurrentUser -n "CN=localhost"
```

<span data-ttu-id="e56c4-138">本示例查找的文件名的证书的主题名称为"CN = localhost"，在个人存储当前用户的并输出完整的目录路径。</span><span class="sxs-lookup"><span data-stu-id="e56c4-138">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User and output the full directory path.</span></span>

```
FindPrivateKey My CurrentUser -n "CN=localhost" -a
```

<span data-ttu-id="e56c4-139">此示例在“本地计算机”的“个人”存储区中查找指纹为 "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" 的证书的文件名。</span><span class="sxs-lookup"><span data-stu-id="e56c4-139">This example finds the filename of the certificate with a thumbprint of "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", in the Personal store of the Local Computer.</span></span>

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"
```
