---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 994e5146e9cf49a9b31396d0b51e7be83bbb3cfb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964780"
---
# <a name="iwpfhostsupport"></a><span data-ttu-id="f0808-102">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="f0808-102">IWpfHostSupport</span></span>
<span data-ttu-id="f0808-103">通过 presentationhost.exe 托管[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]内容的应用程序实现此接口, 以在主机和 presentationhost.exe 之间提供集成点。</span><span class="sxs-lookup"><span data-stu-id="f0808-103">Applications that host [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content via PresentationHost.exe implement this interface to provide a point of integration between the host and PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0808-104">备注</span><span class="sxs-lookup"><span data-stu-id="f0808-104">Remarks</span></span>  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]<span data-ttu-id="f0808-105">诸如 Web 浏览器之类的应用[!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]程序可以承载[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]内容, 包括和松散 XAML。</span><span class="sxs-lookup"><span data-stu-id="f0808-105">applications such as Web browsers can host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content, including [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML.</span></span> <span data-ttu-id="f0808-106">若要[!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]承载内容[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] , 应用程序将创建[WebBrowser 控件](https://go.microsoft.com/fwlink/?LinkId=97911)的实例。</span><span class="sxs-lookup"><span data-stu-id="f0808-106">To host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications create an instance of the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span> <span data-ttu-id="f0808-107">若要托管, [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]将创建 presentationhost.exe 的实例, 该实例向宿主提供承载[!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]的内容, 以便在[WebBrowser 控件](https://go.microsoft.com/fwlink/?LinkId=97911)中显示。</span><span class="sxs-lookup"><span data-stu-id="f0808-107">To be hosted, [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] creates an instance of PresentationHost.exe, which provides the hosted [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content to the host for display in the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span>  
  
 <span data-ttu-id="f0808-108">启用的集成`IWpfHostSupport`允许 presentationhost.exe 执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="f0808-108">The integration enabled by `IWpfHostSupport` allows PresentationHost.exe to:</span></span>  
  
- <span data-ttu-id="f0808-109">发现并注册到主机应用程序感兴趣的原始输入设备 (人机接口设备)。</span><span class="sxs-lookup"><span data-stu-id="f0808-109">Discover and register with the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
- <span data-ttu-id="f0808-110">从已注册的原始输入设备接收输入消息, 并将相应的消息转发到主机应用程序。</span><span class="sxs-lookup"><span data-stu-id="f0808-110">Receive input messages from the registered raw input devices and forward appropriate messages to the host application.</span></span>  
  
- <span data-ttu-id="f0808-111">查询主机应用程序以获取自定义进度和错误用户界面。</span><span class="sxs-lookup"><span data-stu-id="f0808-111">Query the host application for custom progress and error user interfaces.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f0808-112">此 API 预期仅支持在本地客户端计算机上使用</span><span class="sxs-lookup"><span data-stu-id="f0808-112">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="f0808-113">成员</span><span class="sxs-lookup"><span data-stu-id="f0808-113">Members</span></span>  
  
|<span data-ttu-id="f0808-114">成员</span><span class="sxs-lookup"><span data-stu-id="f0808-114">Member</span></span>|<span data-ttu-id="f0808-115">描述</span><span class="sxs-lookup"><span data-stu-id="f0808-115">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f0808-116">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="f0808-116">GetRawInputDevices</span></span>](getrawinputdevices.md)|<span data-ttu-id="f0808-117">允许 PresentationHost.exe 发现主机应用程序感兴趣的原始输入的设备（人机接口设备）。</span><span class="sxs-lookup"><span data-stu-id="f0808-117">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>|  
|[<span data-ttu-id="f0808-118">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="f0808-118">FilterInputMessage</span></span>](filterinputmessage.md)|<span data-ttu-id="f0808-119">除非返回 E_NOTIMP，否则每当收到一条消息时都会由 PresentationHost.exe 调用。</span><span class="sxs-lookup"><span data-stu-id="f0808-119">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>|  
|[<span data-ttu-id="f0808-120">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="f0808-120">GetCustomUI</span></span>](getcustomui.md)|<span data-ttu-id="f0808-121">默认情况下, Presentationhost.exe 提供其自己的部署进度以及部署 WPF 内容时显示的部署错误用户界面。</span><span class="sxs-lookup"><span data-stu-id="f0808-121">By default, PresentationHost.exe provides its own deployment progress and deployment error user interfaces that are displayed when WPF content is deployed.</span></span>|
