---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 85309e46403b2f22f9afb760d4c4ae370c39246b
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004093"
---
# <a name="iwpfhostsupport"></a><span data-ttu-id="e8a13-102">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="e8a13-102">IWpfHostSupport</span></span>
<span data-ttu-id="e8a13-103">通过 Presentationhost.exe 承载 @no__t 0 内容的应用程序实现此接口，以提供主机与 Presentationhost.exe 之间的集成点。</span><span class="sxs-lookup"><span data-stu-id="e8a13-103">Applications that host [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content via PresentationHost.exe implement this interface to provide a point of integration between the host and PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8a13-104">备注</span><span class="sxs-lookup"><span data-stu-id="e8a13-104">Remarks</span></span>  
 <span data-ttu-id="e8a13-105">@no__t 的应用程序（例如 Web 浏览器）可以承载 WPF 内容，包括 @no__t 1 和松散 XAML。</span><span class="sxs-lookup"><span data-stu-id="e8a13-105">[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications such as Web browsers can host WPF content, including [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML.</span></span> <span data-ttu-id="e8a13-106">若要承载 WPF 内容，[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] 应用程序创建[WebBrowser 控件](https://go.microsoft.com/fwlink/?LinkId=97911)的实例。</span><span class="sxs-lookup"><span data-stu-id="e8a13-106">To host WPF content, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications create an instance of the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span> <span data-ttu-id="e8a13-107">若要承载，WPF 将创建 Presentationhost.exe 的一个实例，该实例向宿主提供承载的 WPF 内容以显示在[WebBrowser 控件](https://go.microsoft.com/fwlink/?LinkId=97911)中。</span><span class="sxs-lookup"><span data-stu-id="e8a13-107">To be hosted, WPF creates an instance of PresentationHost.exe, which provides the hosted WPF content to the host for display in the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span>  
  
 <span data-ttu-id="e8a13-108">@No__t 启用的集成允许 Presentationhost.exe 执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e8a13-108">The integration enabled by `IWpfHostSupport` allows PresentationHost.exe to:</span></span>  
  
- <span data-ttu-id="e8a13-109">发现并注册到主机应用程序感兴趣的原始输入设备（人机接口设备）。</span><span class="sxs-lookup"><span data-stu-id="e8a13-109">Discover and register with the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
- <span data-ttu-id="e8a13-110">从已注册的原始输入设备接收输入消息，并将相应的消息转发到主机应用程序。</span><span class="sxs-lookup"><span data-stu-id="e8a13-110">Receive input messages from the registered raw input devices and forward appropriate messages to the host application.</span></span>  
  
- <span data-ttu-id="e8a13-111">查询主机应用程序以获取自定义进度和错误用户界面。</span><span class="sxs-lookup"><span data-stu-id="e8a13-111">Query the host application for custom progress and error user interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e8a13-112">此 API 预期仅支持在本地客户端计算机上使用</span><span class="sxs-lookup"><span data-stu-id="e8a13-112">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="e8a13-113">成员</span><span class="sxs-lookup"><span data-stu-id="e8a13-113">Members</span></span>  
  
|<span data-ttu-id="e8a13-114">成员</span><span class="sxs-lookup"><span data-stu-id="e8a13-114">Member</span></span>|<span data-ttu-id="e8a13-115">描述</span><span class="sxs-lookup"><span data-stu-id="e8a13-115">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e8a13-116">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="e8a13-116">GetRawInputDevices</span></span>](getrawinputdevices.md)|<span data-ttu-id="e8a13-117">允许 PresentationHost.exe 发现主机应用程序感兴趣的原始输入的设备（人机接口设备）。</span><span class="sxs-lookup"><span data-stu-id="e8a13-117">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>|  
|[<span data-ttu-id="e8a13-118">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="e8a13-118">FilterInputMessage</span></span>](filterinputmessage.md)|<span data-ttu-id="e8a13-119">除非返回 E_NOTIMP，否则每当收到一条消息时都会由 PresentationHost.exe 调用。</span><span class="sxs-lookup"><span data-stu-id="e8a13-119">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>|  
|[<span data-ttu-id="e8a13-120">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="e8a13-120">GetCustomUI</span></span>](getcustomui.md)|<span data-ttu-id="e8a13-121">默认情况下，Presentationhost.exe 提供其自己的部署进度以及部署 WPF 内容时显示的部署错误用户界面。</span><span class="sxs-lookup"><span data-stu-id="e8a13-121">By default, PresentationHost.exe provides its own deployment progress and deployment error user interfaces that are displayed when WPF content is deployed.</span></span>|
