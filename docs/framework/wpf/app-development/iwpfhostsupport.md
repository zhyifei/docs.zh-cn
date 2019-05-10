---
title: IWpfHostSupport
ms.date: 03/30/2017
helpviewer_keywords:
- IWpfHostSupport interface [WPF]
ms.assetid: cc5a0281-de81-4cc1-87e4-0e46b1a811e9
ms.openlocfilehash: 97a120c57624ada32e6661bd8a613c4ea1d01b2f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64591393"
---
# <a name="iwpfhostsupport"></a><span data-ttu-id="b18df-102">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="b18df-102">IWpfHostSupport</span></span>
<span data-ttu-id="b18df-103">托管的应用程序[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]内容 PresentationHost.exe 通过实现此接口可提供的主机和 PresentationHost.exe 之间的集成点。</span><span class="sxs-lookup"><span data-stu-id="b18df-103">Applications that host [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] content via PresentationHost.exe implement this interface to provide a point of integration between the host and PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b18df-104">备注</span><span class="sxs-lookup"><span data-stu-id="b18df-104">Remarks</span></span>  
 [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] <span data-ttu-id="b18df-105">应用程序，如 Web 浏览器可以托管[!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]内容，包括[!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)]宽松 XAML。</span><span class="sxs-lookup"><span data-stu-id="b18df-105">applications such as Web browsers can host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content, including [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] and loose XAML.</span></span> <span data-ttu-id="b18df-106">到主机[!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]内容，[!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]应用程序创建的实例[WebBrowser 控件](https://go.microsoft.com/fwlink/?LinkId=97911)。</span><span class="sxs-lookup"><span data-stu-id="b18df-106">To host [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content, [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] applications create an instance of the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span> <span data-ttu-id="b18df-107">要托管[!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]创建的 PresentationHost.exe，提供了托管实例[!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)]所在的主机中的显示内容[WebBrowser 控件](https://go.microsoft.com/fwlink/?LinkId=97911)。</span><span class="sxs-lookup"><span data-stu-id="b18df-107">To be hosted, [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] creates an instance of PresentationHost.exe, which provides the hosted [!INCLUDE[TLA#tla_titlewinclient](../../../../includes/tlasharptla-titlewinclient-md.md)] content to the host for display in the [WebBrowser control](https://go.microsoft.com/fwlink/?LinkId=97911).</span></span>  
  
 <span data-ttu-id="b18df-108">通过启用集成`IWpfHostSupport`允许 PresentationHost.exe 到：</span><span class="sxs-lookup"><span data-stu-id="b18df-108">The integration enabled by `IWpfHostSupport` allows PresentationHost.exe to:</span></span>  
  
- <span data-ttu-id="b18df-109">发现并注册与主机应用程序感兴趣的原始输入设备 （人机接口设备）。</span><span class="sxs-lookup"><span data-stu-id="b18df-109">Discover and register with the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>  
  
- <span data-ttu-id="b18df-110">接收输入的消息从已注册的原始输入的设备和适当的消息转发到主机应用程序。</span><span class="sxs-lookup"><span data-stu-id="b18df-110">Receive input messages from the registered raw input devices and forward appropriate messages to the host application.</span></span>  
  
- <span data-ttu-id="b18df-111">查询进度和错误的自定义用户界面的主机应用程序。</span><span class="sxs-lookup"><span data-stu-id="b18df-111">Query the host application for custom progress and error user interfaces.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b18df-112">此 API 预期仅支持在本地客户端计算机上使用</span><span class="sxs-lookup"><span data-stu-id="b18df-112">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="b18df-113">成员</span><span class="sxs-lookup"><span data-stu-id="b18df-113">Members</span></span>  
  
|<span data-ttu-id="b18df-114">成员</span><span class="sxs-lookup"><span data-stu-id="b18df-114">Member</span></span>|<span data-ttu-id="b18df-115">描述</span><span class="sxs-lookup"><span data-stu-id="b18df-115">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b18df-116">GetRawInputDevices</span><span class="sxs-lookup"><span data-stu-id="b18df-116">GetRawInputDevices</span></span>](getrawinputdevices.md)|<span data-ttu-id="b18df-117">允许 PresentationHost.exe 发现主机应用程序感兴趣的原始输入的设备（人机接口设备）。</span><span class="sxs-lookup"><span data-stu-id="b18df-117">Allows PresentationHost.exe to discover the raw input devices (Human Interface Devices) that the host application is interested in.</span></span>|  
|[<span data-ttu-id="b18df-118">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="b18df-118">FilterInputMessage</span></span>](filterinputmessage.md)|<span data-ttu-id="b18df-119">除非返回 E_NOTIMP，否则每当收到一条消息时都会由 PresentationHost.exe 调用。</span><span class="sxs-lookup"><span data-stu-id="b18df-119">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>|  
|[<span data-ttu-id="b18df-120">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="b18df-120">GetCustomUI</span></span>](getcustomui.md)|<span data-ttu-id="b18df-121">默认情况下，PresentationHost.exe 提供其自己的部署进度和部署错误会显示部署的 WPF 内容时的用户界面。</span><span class="sxs-lookup"><span data-stu-id="b18df-121">By default, PresentationHost.exe provides its own deployment progress and deployment error user interfaces that are displayed when WPF content is deployed.</span></span>|
