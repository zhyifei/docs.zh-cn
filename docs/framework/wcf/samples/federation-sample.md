---
title: "联合示例"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e9da0ca-e925-4644-aa96-8bfaf649d4bb
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6c87984b08a073f37dcf155a39fab0f5e580e985
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="federation-sample"></a><span data-ttu-id="4cd75-102">联合示例</span><span class="sxs-lookup"><span data-stu-id="4cd75-102">Federation Sample</span></span>
<span data-ttu-id="4cd75-103">本示例演示联合安全。</span><span class="sxs-lookup"><span data-stu-id="4cd75-103">This sample demonstrates federated security.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="4cd75-104">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="4cd75-104">Sample Details</span></span>  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="4cd75-105"> 为通过 `wsFederationHttpBinding` 部署联合安全体系结构提供支持。</span><span class="sxs-lookup"><span data-stu-id="4cd75-105"> provides support for deploying federated security architectures through the `wsFederationHttpBinding`.</span></span> <span data-ttu-id="4cd75-106">`wsFederationHttpBinding` 提供安全可靠并且可互操作的绑定，该绑定中使用 HTTP 作为请求/回复通信的基础传输机制，并使用文本/XML 作为编码的联网格式。</span><span class="sxs-lookup"><span data-stu-id="4cd75-106">The `wsFederationHttpBinding` provides a secure, reliable, and interoperable binding that involves the use of HTTP as the underlying transport mechanism for request/reply communication, and Text/XML as the wire format for encoding.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="4cd75-107">中的联合身份验证[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]，请参阅[联合身份验证](../../../../docs/framework/wcf/feature-details/federation.md)。</span><span class="sxs-lookup"><span data-stu-id="4cd75-107"> Federation in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], see [Federation](../../../../docs/framework/wcf/feature-details/federation.md).</span></span>  
  
 <span data-ttu-id="4cd75-108">此方案包括 4 个部分：</span><span class="sxs-lookup"><span data-stu-id="4cd75-108">The scenario is made up of 4 pieces:</span></span>  
  
-   <span data-ttu-id="4cd75-109">BookStore 服务</span><span class="sxs-lookup"><span data-stu-id="4cd75-109">BookStore service</span></span>  
  
-   <span data-ttu-id="4cd75-110">BookStore STS</span><span class="sxs-lookup"><span data-stu-id="4cd75-110">BookStore STS</span></span>  
  
-   <span data-ttu-id="4cd75-111">HomeRealm STS</span><span class="sxs-lookup"><span data-stu-id="4cd75-111">HomeRealm STS</span></span>  
  
-   <span data-ttu-id="4cd75-112">BookStore 客户端</span><span class="sxs-lookup"><span data-stu-id="4cd75-112">BookStore Client</span></span>  
  
 <span data-ttu-id="4cd75-113">BookStore 服务支持两个操作：`BrowseBooks` 和 `BuyBook`。</span><span class="sxs-lookup"><span data-stu-id="4cd75-113">The BookStore service supports two operations, `BrowseBooks` and `BuyBook`.</span></span> <span data-ttu-id="4cd75-114">它允许匿名访问 `BrowseBooks` 操作，但需要经过身份验证才能访问 `BuyBooks` 操作。</span><span class="sxs-lookup"><span data-stu-id="4cd75-114">It allows anonymous access to the `BrowseBooks` operation, but requires authenticated access to access the `BuyBooks` operation.</span></span> <span data-ttu-id="4cd75-115">身份验证采用由 BookStore STS 颁发的令牌的形式。</span><span class="sxs-lookup"><span data-stu-id="4cd75-115">The authentication takes the form of a token issued by the BookStore STS.</span></span> <span data-ttu-id="4cd75-116">BookStore 服务的配置文件使用 `wsFederationHttpBinding` 将客户端指向 BookStore STS。</span><span class="sxs-lookup"><span data-stu-id="4cd75-116">The configuration file for the BookStore Service points clients to the BookStore STS using the `wsFederationHttpBinding`.</span></span>  
  
```xml  
<wsFederationHttpBinding>  
<!-- This is the Service binding for the BuyBooks endpoint. It redirects clients to the BookStore STS -->  
    <binding name='BuyBookBinding'>  
        <security mode="Message">  
            <message>  
                <issuerMetadata  
  address='http://localhost/FederationSample/BookStoreSTS/STS.svc/mex' >  
                    <identity>  
                        <dns value ='BookStoreSTS.com'/>  
                    </identity>  
                </issuerMetadata>  
            </message>  
        </security>  
    </binding>  
</wsFederationHttpBinding>  
```  
  
 <span data-ttu-id="4cd75-117">BookStore STS 然后要求客户端使用 HomeRealm STS 颁发的令牌进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="4cd75-117">The BookStore STS then requires that clients authenticate using a token issued by the HomeRealm STS.</span></span> <span data-ttu-id="4cd75-118">同样，BookStore STS 的配置文件使用 `wsFederationHttpBinding` 将客户端指向 HomeRealm STS。</span><span class="sxs-lookup"><span data-stu-id="4cd75-118">Again, the configuration file for the BookStore STS points clients to the HomeRealm STS using the `wsFederationHttpBinding`.</span></span>  
  
```xml  
<wsFederationHttpBinding>  
 <!-- This is the binding for the clients requesting tokens from this STS. It redirects clients to the HomeRealm STS -->  
    <binding name='BookStoreSTSBinding'>  
        <security mode='Message'>  
            <message>  
                <issuerMetadata  
 address='http://localhost/FederationSample/HomeRealmSTS/STS.svc/mex' >  
                    <identity>  
                        <dns value ='HomeRealmSTS.com' />  
                    </identity>  
                </issuerMetadata>  
            </message>  
        </security>  
    </binding>  
</wsFederationHttpBinding>  
```  
  
 <span data-ttu-id="4cd75-119">访问 `BuyBook` 操作时的事件序列如下：</span><span class="sxs-lookup"><span data-stu-id="4cd75-119">The sequence of events when accessing the `BuyBook` operation is as follows:</span></span>  
  
1.  <span data-ttu-id="4cd75-120">客户端使用 Windows 凭据向 HomeRealm STS 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="4cd75-120">The client authenticates to the HomeRealm STS using Windows credentials.</span></span>  
  
2.  <span data-ttu-id="4cd75-121">HomeRealm STS 颁发一个令牌，该令牌可用于向 BookStore STS 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="4cd75-121">The HomeRealm STS issues a token that can be used to authenticate to the BookStore STS.</span></span>  
  
3.  <span data-ttu-id="4cd75-122">客户端使用 HomeRealm STS 颁发的令牌向 BookStore STS 进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="4cd75-122">The client authenticates to the BookStore STS using the token issued by the HomeRealm STS.</span></span>  
  
4.  <span data-ttu-id="4cd75-123">BookStore STS 颁发一个令牌，该令牌可用于向 BookStore 服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="4cd75-123">The BookStore STS issues a token that can be used to authenticate to the BookStore Service.</span></span>  
  
5.  <span data-ttu-id="4cd75-124">客户端使用 BookStore STS 颁发的令牌向 BookStore 服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="4cd75-124">The client authenticates to the BookStore service using the token issued by the BookStore STS.</span></span>  
  
6.  <span data-ttu-id="4cd75-125">客户端访问 `BuyBook` 操作。</span><span class="sxs-lookup"><span data-stu-id="4cd75-125">The client accesses the `BuyBook` operation.</span></span>  
  
 <span data-ttu-id="4cd75-126">有关如何设置和运行此示例的信息，请参见以下说明。</span><span class="sxs-lookup"><span data-stu-id="4cd75-126">See the following instructions about how to set up and run this sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4cd75-127">你必须拥有写入权限**wwwroot**目录运行此示例。</span><span class="sxs-lookup"><span data-stu-id="4cd75-127">You must have Write permissions to the **wwwroot** directory to run this sample.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4cd75-128">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="4cd75-128">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="4cd75-129">打开 SDK 命令窗口。</span><span class="sxs-lookup"><span data-stu-id="4cd75-129">Open the SDK command window.</span></span> <span data-ttu-id="4cd75-130">在示例路径中运行 Setup.bat。</span><span class="sxs-lookup"><span data-stu-id="4cd75-130">In the sample path, run Setup.bat.</span></span> <span data-ttu-id="4cd75-131">这将创建示例所需的虚拟目录，并使用相应的权限安装所需的证书。</span><span class="sxs-lookup"><span data-stu-id="4cd75-131">This creates the virtual directories required for the sample and installs the required certificates with appropriate permissions.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4cd75-132">Setup.bat 批处理文件设计为通过 Windows SDK 命令提示运行。</span><span class="sxs-lookup"><span data-stu-id="4cd75-132">The Setup.bat batch file is designed to be run from a Windows SDK Command Prompt.</span></span> <span data-ttu-id="4cd75-133">这要求 MSSDK 环境变量指向 SDK 的安装目录。</span><span class="sxs-lookup"><span data-stu-id="4cd75-133">It requires that the MSSDK environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="4cd75-134">将在 Windows SDK 命令提示中自动设置此环境变量。</span><span class="sxs-lookup"><span data-stu-id="4cd75-134">This environment variable is automatically set within a Windows SDK Command Prompt.</span></span> <span data-ttu-id="4cd75-135">在 [!INCLUDE[wv](../../../../includes/wv-md.md)] 上，必须确保已安装 IIS 6.0 管理兼容性，因为安装程序将使用 IIS 管理员脚本。</span><span class="sxs-lookup"><span data-stu-id="4cd75-135">On [!INCLUDE[wv](../../../../includes/wv-md.md)], you must ensure that IIS 6.0 Management Compatibility is installed because the set up uses IIS administrator scripts.</span></span> <span data-ttu-id="4cd75-136">在 [!INCLUDE[wv](../../../../includes/wv-md.md)] 上运行安装脚本需要具有管理员特权。</span><span class="sxs-lookup"><span data-stu-id="4cd75-136">Running the set-up script on [!INCLUDE[wv](../../../../includes/wv-md.md)] requires administrator privileges.</span></span>  
  
2.  <span data-ttu-id="4cd75-137">在 Visual Studio 中打开 FederationSample.sln，并选择**生成解决方案**从**生成**菜单。</span><span class="sxs-lookup"><span data-stu-id="4cd75-137">Open FederationSample.sln in Visual Studio and select **Build Solution** from the **Build** menu.</span></span> <span data-ttu-id="4cd75-138">这将生成通用项目文件、Bookstore 服务、Bookstore STS、HomeRealm STS 并将它们部署到 IIS 中。</span><span class="sxs-lookup"><span data-stu-id="4cd75-138">This builds the common project files, Bookstore service, Bookstore STS, HomeRealm STS, and deploys them in IIS.</span></span> <span data-ttu-id="4cd75-139">还将生成 Bookstore 客户端应用程序，并将可执行文件 BookStoreClient.exe 放入 FederationSample\BookStoreClient\bin\Debug 文件夹。</span><span class="sxs-lookup"><span data-stu-id="4cd75-139">This also builds the Bookstore client application and places the executable BookStoreClient.exe in the FederationSample\BookStoreClient\bin\Debug folder.</span></span>  
  
3.  <span data-ttu-id="4cd75-140">双击 BookStoreClient.exe。</span><span class="sxs-lookup"><span data-stu-id="4cd75-140">Double-click BookStoreClient.exe.</span></span> <span data-ttu-id="4cd75-141">将显示 BookStoreClient 窗口。</span><span class="sxs-lookup"><span data-stu-id="4cd75-141">The BookStoreClient window is displayed.</span></span>  
  
4.  <span data-ttu-id="4cd75-142">你可以通过单击浏览书店中供应的图书**浏览丛书**。</span><span class="sxs-lookup"><span data-stu-id="4cd75-142">You can browse the books available in the bookstore by clicking **Browse Books**.</span></span>  
  
5.  <span data-ttu-id="4cd75-143">若要购买某一本图书，列表中选择书籍，然后单击**购买书籍**。</span><span class="sxs-lookup"><span data-stu-id="4cd75-143">To purchase a particular book, select the book in the list and click **Buy Book**.</span></span> <span data-ttu-id="4cd75-144">该应用程序将启动，并使用 Windows 身份验证和 HomeRealm 安全令牌服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="4cd75-144">The application starts up and authenticates using Windows authentication with the HomeRealm Security Token Service.</span></span>  
  
     <span data-ttu-id="4cd75-145">此示例配置为允许用户购买价格等于或低于 15 美元的图书。</span><span class="sxs-lookup"><span data-stu-id="4cd75-145">The sample is configured to allow users to purchase books that cost $15 or less.</span></span> <span data-ttu-id="4cd75-146">尝试购买价格超过 15 美元的图书将导致客户端从 BookStore 服务获得“拒绝访问”消息。</span><span class="sxs-lookup"><span data-stu-id="4cd75-146">Attempting to buy books that cost more than $15 results in the client getting an Access Denied message from the Book Store Service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4cd75-147">此示例不会在用户购买图书后更新其信用限额。</span><span class="sxs-lookup"><span data-stu-id="4cd75-147">The sample does not update the user’s credit limit after a purchase.</span></span> <span data-ttu-id="4cd75-148">您可以在用户的（固定）信用限额内反复购买图书。</span><span class="sxs-lookup"><span data-stu-id="4cd75-148">You can repeatedly purchase books within the user’s (fixed) credit limit.</span></span>  
  
#### <a name="to-clean-up"></a><span data-ttu-id="4cd75-149">清理</span><span class="sxs-lookup"><span data-stu-id="4cd75-149">To clean up</span></span>  
  
1.  <span data-ttu-id="4cd75-150">运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="4cd75-150">Run Cleanup.bat.</span></span> <span data-ttu-id="4cd75-151">这将删除安装过程中创建的虚拟目录，并移除安装过程中安装的证书。</span><span class="sxs-lookup"><span data-stu-id="4cd75-151">This deletes the virtual directories that were created during set up and also removes the certificates installed during setup.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4cd75-152">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="4cd75-152">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4cd75-153">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="4cd75-153">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4cd75-154">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="4cd75-154">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4cd75-155">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="4cd75-155">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\Federation`  
  
## <a name="see-also"></a><span data-ttu-id="4cd75-156">请参阅</span><span class="sxs-lookup"><span data-stu-id="4cd75-156">See Also</span></span>
