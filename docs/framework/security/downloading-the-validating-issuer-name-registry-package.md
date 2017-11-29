---
title: "下载验证颁发者名称注册表包"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ff8b0014-c5d4-4614-90f0-13fcc0ba777a
caps.latest.revision: "3"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: d7aa4e4010da70f90bb18db9cd4e8179925bb58d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="downloading-the-validating-issuer-name-registry-package"></a><span data-ttu-id="d68ce-102">下载验证颁发者名称注册表包</span><span class="sxs-lookup"><span data-stu-id="d68ce-102">Downloading the Validating Issuer Name Registry Package</span></span>
<span data-ttu-id="d68ce-103">本主题讨论如何在项目中下载和使用验证颁发者名称注册表 (VINR)。</span><span class="sxs-lookup"><span data-stu-id="d68ce-103">This topic discusses how to download and use the Validating Issuer Name Registry (VINR) in your project.</span></span>  
  
## <a name="downloading-the-validating-issuer-name-registry"></a><span data-ttu-id="d68ce-104">下载验证颁发者名称注册表</span><span class="sxs-lookup"><span data-stu-id="d68ce-104">Downloading the Validating Issuer Name Registry</span></span>  
 <span data-ttu-id="d68ce-105">VINR 可用作 NuGet 包，可将必要程序集和引用添加到项目。</span><span class="sxs-lookup"><span data-stu-id="d68ce-105">The VINR is available as a NuGet package, which adds the necessary assemblies and references to your project.</span></span> <span data-ttu-id="d68ce-106">如果尚未安装 NuGet，请转到 [nuget.org](http://nuget.org) 进行安装。</span><span class="sxs-lookup"><span data-stu-id="d68ce-106">If you do not already have NuGet installed, go to [nuget.org](http://nuget.org) to install it.</span></span> <span data-ttu-id="d68ce-107">访问 NuGet 上的扩展页面，查看扩展的版本历史记录：[NuGet 上的 Microsoft 验证颁发者名称注册表](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/)</span><span class="sxs-lookup"><span data-stu-id="d68ce-107">You can see the versioning history for the extension by visiting its page on NuGet: [Microsoft Validating Issuer Name Registry on NuGet](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/)</span></span>  
  
#### <a name="downloading-the-validating-issuer-name-registry-by-using-the-package-manager-gui"></a><span data-ttu-id="d68ce-108">使用包管理器 GUI 下载验证颁发者名称注册表</span><span class="sxs-lookup"><span data-stu-id="d68ce-108">Downloading the Validating Issuer Name Registry by using the Package Manager GUI</span></span>  
  
1.  <span data-ttu-id="d68ce-109">在 Visual Studio 中，在解决方案资源管理器中右键单击项目，然后选择“管理 NuGet 包”。</span><span class="sxs-lookup"><span data-stu-id="d68ce-109">In Visual Studio, right-click your project in **Solution Explorer**, and then select **Manage NuGet Packages**.</span></span>  
  
2.  <span data-ttu-id="d68ce-110">在“管理 NuGet 包”窗口中，单击搜索框并输入 `ValidatingIssuerNameRegistry`，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="d68ce-110">In the **Manage NuGet Packages** window, click the search box and enter `ValidatingIssuerNameRegistry` and press **Enter**.</span></span>  
  
3.  <span data-ttu-id="d68ce-111">单击结果窗格中第一个结果的“安装”按钮。</span><span class="sxs-lookup"><span data-stu-id="d68ce-111">From the results pane, click the **Install** button for the first result.</span></span>  
  
4.  <span data-ttu-id="d68ce-112">将开始下载包。</span><span class="sxs-lookup"><span data-stu-id="d68ce-112">The package will begin downloading.</span></span> <span data-ttu-id="d68ce-113">将包添加到项目前，会出现“许可证接受”对话框。</span><span class="sxs-lookup"><span data-stu-id="d68ce-113">Before it is added to your project, the License Acceptance dialog will appear.</span></span> <span data-ttu-id="d68ce-114">如果同意许可条款，请单击“我接受”。</span><span class="sxs-lookup"><span data-stu-id="d68ce-114">If you agree to the license terms, click **I Accept**.</span></span>  
  
5.  <span data-ttu-id="d68ce-115">将下载并添加最新 VINR 程序集到项目。</span><span class="sxs-lookup"><span data-stu-id="d68ce-115">The latest VINR assemblies will be downloaded and added to your project.</span></span>  
  
#### <a name="downloading-the-validating-issuer-name-registry-by-using-the-package-manager-console"></a><span data-ttu-id="d68ce-116">使用包管理器控制台下载验证颁发者名称注册表</span><span class="sxs-lookup"><span data-stu-id="d68ce-116">Downloading the Validating Issuer Name Registry by using the Package Manager Console</span></span>  
  
1.  <span data-ttu-id="d68ce-117">在 Visual Studio 中，依次单击“工具”、“库包管理器”和“包管理器控制台”。</span><span class="sxs-lookup"><span data-stu-id="d68ce-117">In Visual Studio, click **Tools**, **Library Package Manager**, and then **Package Manager Console**.</span></span>  
  
2.  <span data-ttu-id="d68ce-118">随即出现“包管理器控制台”。</span><span class="sxs-lookup"><span data-stu-id="d68ce-118">The **Package Manager Console** appears.</span></span> <span data-ttu-id="d68ce-119">输入以下文本并按 Enter：</span><span class="sxs-lookup"><span data-stu-id="d68ce-119">Enter the following text and press **Enter**:</span></span>  
  
    ```powershell  
    Install-Package System.IdentityModel.Tokens.ValidatingIssuerNameRegistry  
    ```  
  
3.  <span data-ttu-id="d68ce-120">将下载并添加最新 VINR 程序集到项目。</span><span class="sxs-lookup"><span data-stu-id="d68ce-120">The latest VINR assemblies will be downloaded and added to your project.</span></span>
