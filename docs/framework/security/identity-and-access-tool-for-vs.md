---
title: 适用于 Visual Studio 2012 的标识和访问工具
ms.date: 03/30/2017
ms.assetid: 87b8f8f2-4074-44fd-9fd6-08278e877390
author: BrucePerlerMS
ms.openlocfilehash: 1177048d8124c955220605e52dde539b84510cba
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48584152"
---
# <a name="identity-and-access-tool-for-visual-studio-2012"></a><span data-ttu-id="26e7e-102">适用于 Visual Studio 2012 的标识和访问工具</span><span class="sxs-lookup"><span data-stu-id="26e7e-102">Identity and Access Tool for Visual Studio 2012</span></span>
<span data-ttu-id="26e7e-103">本主题描述了适用于 Visual Studio 11 的新的标识和访问工具。</span><span class="sxs-lookup"><span data-stu-id="26e7e-103">This topic describes the new Identity and Access Tool for Visual Studio 11.</span></span> <span data-ttu-id="26e7e-104">可以从以下 URL 下载此工具： [ https://go.microsoft.com/fwlink/?LinkID=245849 ](https://go.microsoft.com/fwlink/?LinkID=245849)或直接从 Visual Studio 11 中搜索"标识"直接在扩展管理器中。</span><span class="sxs-lookup"><span data-stu-id="26e7e-104">You can download this tool from the following URL: [https://go.microsoft.com/fwlink/?LinkID=245849](https://go.microsoft.com/fwlink/?LinkID=245849) or directly from within Visual Studio 11 by searching for "identity" directly in the Extensions Manager.</span></span>  
  
 <span data-ttu-id="26e7e-105">适用于 Visual Studio 11 的新的标识和访问工具提供了开发时间大大减少的体验，并具有如下要点：</span><span class="sxs-lookup"><span data-stu-id="26e7e-105">The Identity and Access Tool for Visual Studio 11 delivers a dramatically simplified development-time experience with the following highlights:</span></span>  
  
-   <span data-ttu-id="26e7e-106">借助此新工具，您可以使用 Web 应用程序项目类型和目标 IIS Express 进行开发。</span><span class="sxs-lookup"><span data-stu-id="26e7e-106">Using the new tool, you can develop using web applications project types and target IIS express.</span></span>  
  
-   <span data-ttu-id="26e7e-107">与一般仅保护性身份验证不同，利用此新工具，您可以指定本地主页领域发现页/控制器（或处理应用程序中的身份验证体验的任何其他终结点），并且 WIF 会将所有未经身份验证的请求配置为转到此处，而不是将其重定向到 STS。</span><span class="sxs-lookup"><span data-stu-id="26e7e-107">Unlike with the blanket protection-only authentication, with the new tool, you can specify your local home realm discovery page/controller (or any other endpoint handling the authentication experience within your application) and WIF will configure all unauthenticated requests to go there, instead of redirecting them to the STS.</span></span>  
  
-   <span data-ttu-id="26e7e-108">此工具包括一项在启动调试会话时运行于你的本地计算机上的测试安全令牌服务 (STS)。</span><span class="sxs-lookup"><span data-stu-id="26e7e-108">The tool includes a test Security Token Service (STS) which runs on your local machine when you launch a debug session.</span></span> <span data-ttu-id="26e7e-109">因此，您不再需要创建自定义 STS 项目并对其进行调整即可获得测试应用程序所需的声明。</span><span class="sxs-lookup"><span data-stu-id="26e7e-109">Therefore, you no longer need to create custom STS projects and tweak them in order to get the claims you need to test your applications.</span></span> <span data-ttu-id="26e7e-110">声明类型和值是可完全自定义的。</span><span class="sxs-lookup"><span data-stu-id="26e7e-110">The claim types and values are fully customizable.</span></span>  
  
-   <span data-ttu-id="26e7e-111">你可以通过此工具的 UI 直接修改常见设置，而无需编辑 web.config。</span><span class="sxs-lookup"><span data-stu-id="26e7e-111">You can modify common settings directly via the tool’s UI, without the need to edit web.config.</span></span>  
  
-   <span data-ttu-id="26e7e-112">您可以在单个屏幕上使用 Active Directory 联合身份验证服务 (AD FS) 2.0（或其他 WS 联合身份验证提供程序）建立联合身份验证。</span><span class="sxs-lookup"><span data-stu-id="26e7e-112">You can establish federation with Active Directory Federation Services (AD FS) 2.0 (or other WS-Federation providers) in a single screen.</span></span>  
  
-   <span data-ttu-id="26e7e-113">此工具将 Microsoft Azure 访问控制服务 (ACS) 的功能与要使用的所有标识提供程序的复选框列表结合使用：Facebook、Google、Live ID、Yahoo!、任何 OpenID 提供程序以及任何 WS 联合身份验证提供程序。</span><span class="sxs-lookup"><span data-stu-id="26e7e-113">The tool leverages Windows Azure Access Control Service (ACS) capabilities with a simple list of checkboxes for all the identity providers that you want to use: Facebook, Google, Live ID, Yahoo!, any OpenID provider, and any WS-Federation provider.</span></span> <span data-ttu-id="26e7e-114">选择标识提供程序，单击“确定”，然后按 F5，这会自动配置你的应用程序和 ACS，并且你的测试应用程序将是 ACS 感知的。</span><span class="sxs-lookup"><span data-stu-id="26e7e-114">Select your identity providers, click OK, then F5, and both your application and ACS will be automatically configured and your test application will be ACS-aware.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26e7e-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="26e7e-115">See Also</span></span>  
 [<span data-ttu-id="26e7e-116">WIF 功能</span><span class="sxs-lookup"><span data-stu-id="26e7e-116">WIF Features</span></span>](../../../docs/framework/security/wif-features.md)
