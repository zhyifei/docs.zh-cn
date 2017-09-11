---
title: "下载 JSON Web 标记处理程序包"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d12b3f5b-f1f1-4a9d-a159-0c13e5976c90
caps.latest.revision: 3
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: d3821ff1da945df7c6e07e5baf69730173eacc87
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="downloading-the-json-web-token-handler-package"></a><span data-ttu-id="a687b-102">下载 JSON Web 标记处理程序包</span><span class="sxs-lookup"><span data-stu-id="a687b-102">Downloading the JSON Web Token Handler Package</span></span>
<span data-ttu-id="a687b-103">本主题讨论了如何在项目中下载和使用 JSON Web 令牌处理程序。</span><span class="sxs-lookup"><span data-stu-id="a687b-103">This topic discusses how to download and use the JSON Web Token Handler in your project.</span></span>  
  
## <a name="downloading-the-json-web-token-handler"></a><span data-ttu-id="a687b-104">下载 JSON Web 标记处理程序</span><span class="sxs-lookup"><span data-stu-id="a687b-104">Downloading the JSON Web Token Handler</span></span>  
 <span data-ttu-id="a687b-105">JSON Web 令牌处理程序扩展可用作 NuGet 程序包，可将必要程序集和引用添加到项目。</span><span class="sxs-lookup"><span data-stu-id="a687b-105">The JSON Web Token Handler extension is available as a NuGet package, which adds the necessary assemblies and references to your project.</span></span> <span data-ttu-id="a687b-106">如果尚未安装 NuGet，请转到 [nuget.org](http://nuget.org) 进行安装。</span><span class="sxs-lookup"><span data-stu-id="a687b-106">If you do not already have NuGet installed, go to [nuget.org](http://nuget.org) to install it.</span></span> <span data-ttu-id="a687b-107">访问 NuGet 上的扩展页面，查看扩展的版本历史记录：[NuGet 上的 JSON Web 令牌处理程序](http://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/)</span><span class="sxs-lookup"><span data-stu-id="a687b-107">You can see the versioning history for the extension by visiting its page on NuGet: [JSON Web Token Handler on NuGet](http://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/)</span></span>  
  
#### <a name="downloading-the-json-web-token-handler-by-using-the-package-manager-gui"></a><span data-ttu-id="a687b-108">使用程序包管理器 GUI 下载 JSON Web 令牌处理程序</span><span class="sxs-lookup"><span data-stu-id="a687b-108">Downloading the JSON Web Token Handler by using the Package Manager GUI</span></span>  
  
1.  <span data-ttu-id="a687b-109">在 Visual Studio 中，在解决方案资源管理器中右键单击项目，然后选择“管理 NuGet 包”。</span><span class="sxs-lookup"><span data-stu-id="a687b-109">In Visual Studio, right-click your project in **Solution Explorer**, and then select **Manage NuGet Packages**.</span></span>  
  
2.  <span data-ttu-id="a687b-110">在“管理 NuGet 包”窗口中，单击搜索框并输入 `JWT Token Handler`，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="a687b-110">In the **Manage NuGet Packages** window, click the search box and enter `JWT Token Handler` and press **Enter**.</span></span>  
  
3.  <span data-ttu-id="a687b-111">单击结果窗格中第一个结果的“安装”按钮。</span><span class="sxs-lookup"><span data-stu-id="a687b-111">From the results pane, click the **Install** button for the first result.</span></span>  
  
4.  <span data-ttu-id="a687b-112">将开始下载包。</span><span class="sxs-lookup"><span data-stu-id="a687b-112">The package will begin downloading.</span></span> <span data-ttu-id="a687b-113">将包添加到项目前，会出现“许可证接受”对话框。</span><span class="sxs-lookup"><span data-stu-id="a687b-113">Before it is added to your project, the License Acceptance dialog will appear.</span></span> <span data-ttu-id="a687b-114">如果同意许可条款，请单击“我接受”。</span><span class="sxs-lookup"><span data-stu-id="a687b-114">If you agree to the license terms, click **I Accept**.</span></span>  
  
5.  <span data-ttu-id="a687b-115">将下载最新的 JSON Web 令牌处理程序程序集并添加到项目。</span><span class="sxs-lookup"><span data-stu-id="a687b-115">The latest JSON Web Token Handler assemblies will be downloaded and added to your project.</span></span>  
  
#### <a name="downloading-the-json-web-token-handler-by-using-the-package-manager-console"></a><span data-ttu-id="a687b-116">使用包管理器控制台下载 JSON Web 令牌处理程序</span><span class="sxs-lookup"><span data-stu-id="a687b-116">Downloading the JSON Web Token Handler by using the Package Manager Console</span></span>  
  
1.  <span data-ttu-id="a687b-117">在 Visual Studio 中，依次单击“工具”、“库包管理器”和“包管理器控制台”。</span><span class="sxs-lookup"><span data-stu-id="a687b-117">In Visual Studio, click **Tools**, **Library Package Manager**, and then **Package Manager Console**.</span></span>  
  
2.  <span data-ttu-id="a687b-118">随即出现“包管理器控制台”。</span><span class="sxs-lookup"><span data-stu-id="a687b-118">The **Package Manager Console** appears.</span></span> <span data-ttu-id="a687b-119">输入以下文本并按 Enter：</span><span class="sxs-lookup"><span data-stu-id="a687b-119">Enter the following text and press **Enter**:</span></span>  
  
    ```powershell  
    Install-Package System.IdentityModel.Tokens.Jwt  
    ```  
  
3.  <span data-ttu-id="a687b-120">将下载最新的 JSON Web 令牌处理程序程序集并添加到项目。</span><span class="sxs-lookup"><span data-stu-id="a687b-120">The latest JSON Web Token Handler assemblies will be downloaded and added to your project.</span></span>

