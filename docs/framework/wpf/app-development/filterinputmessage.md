---
title: FilterInputMessage
ms.date: 03/30/2017
helpviewer_keywords:
- raw input [WPF]
- FilterInputMessage method [WPF]
ms.assetid: 4d74c6cf-7d1d-49ff-96c1-231340ce54f5
ms.openlocfilehash: 1a22071696ca012968e042e15cd8a9f4b876fd9f
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46000773"
---
# <a name="filterinputmessage"></a><span data-ttu-id="fa3a5-102">FilterInputMessage</span><span class="sxs-lookup"><span data-stu-id="fa3a5-102">FilterInputMessage</span></span>
<span data-ttu-id="fa3a5-103">除非返回 E_NOTIMP，否则每当收到一条消息时都会由 PresentationHost.exe 调用。</span><span class="sxs-lookup"><span data-stu-id="fa3a5-103">Called by PresentationHost.exe whenever a message is received unless E_NOTIMPL is returned.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa3a5-104">语法</span><span class="sxs-lookup"><span data-stu-id="fa3a5-104">Syntax</span></span>  
  
```  
HRESULT FilterInputMessage( [in] MSG* pMsg ) ;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fa3a5-105">参数</span><span class="sxs-lookup"><span data-stu-id="fa3a5-105">Parameters</span></span>  
 `pMsg`  
  
 <span data-ttu-id="fa3a5-106">[in] 发送给正在获得原始输入的窗口的 WM_INPUT 消息。</span><span class="sxs-lookup"><span data-stu-id="fa3a5-106">[in] The WM_INPUT message sent to the window that is getting raw input.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="fa3a5-107">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="fa3a5-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="fa3a5-108">HRESULT：</span><span class="sxs-lookup"><span data-stu-id="fa3a5-108">HRESULT:</span></span>  
  
 <span data-ttu-id="fa3a5-109">S_OK - 筛选器未处理该消息，且可能执行进一步处理。</span><span class="sxs-lookup"><span data-stu-id="fa3a5-109">S_OK - The filter did not process the message and further processing may occur.</span></span>  
  
 <span data-ttu-id="fa3a5-110">S_FALSE - 筛选器已处理此消息，且应执行进一步处理。</span><span class="sxs-lookup"><span data-stu-id="fa3a5-110">S_FALSE - The filter processed this message and no further processing should occur.</span></span>  
  
 <span data-ttu-id="fa3a5-111">E_NOTIMPL – 如果返回此值，则[FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md)不会再调用。</span><span class="sxs-lookup"><span data-stu-id="fa3a5-111">E_NOTIMPL – If this value is returned, [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md) is not called again.</span></span> <span data-ttu-id="fa3a5-112">这可能会从以下主机应用程序返回：仅对向 PresentationHost.exe 提供自定义进度和错误用户界面有兴趣且对从 PresentationHost.exe 向自身转发原始输入消息不感兴趣。</span><span class="sxs-lookup"><span data-stu-id="fa3a5-112">This might be returned from a host application that is only interested in providing custom progress and error user interfaces to PresentationHost.exe is not interested in being forwarded raw input messages from PresentationHost.exe.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fa3a5-113">备注</span><span class="sxs-lookup"><span data-stu-id="fa3a5-113">Remarks</span></span>  
 <span data-ttu-id="fa3a5-114">PresentationHost.exe 是各种原始输入设备（包括键盘、鼠标和远程控件）的目标。</span><span class="sxs-lookup"><span data-stu-id="fa3a5-114">PresentationHost.exe is the target of various raw input devices, including keyboard, mice, and remote controls.</span></span> <span data-ttu-id="fa3a5-115">有时，主机应用程序中的行为取决于输入，否则将由 PresentationHost.exe 消耗。</span><span class="sxs-lookup"><span data-stu-id="fa3a5-115">Sometimes, behavior in the host application is dependent on input that would otherwise be consumed by PresentationHost.exe.</span></span> <span data-ttu-id="fa3a5-116">例如，主机应用程序可能依靠接收特定输入消息来确定是否显示特定的用户界面元素。</span><span class="sxs-lookup"><span data-stu-id="fa3a5-116">For example, a host application may depend on receiving certain input messages to determine whether or not to display specific user interface elements.</span></span>  
  
 <span data-ttu-id="fa3a5-117">若要允许主机应用程序接收必要的输入的消息以提供这些行为，PresentationHost.exe 相应原始输入将消息转发到承载的应用程序通过调用[FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md)。</span><span class="sxs-lookup"><span data-stu-id="fa3a5-117">To allow the host application to receive the necessary input messages to provide these behaviors, PresentationHost.exe forwards appropriate raw input messages to the hosted application by calling [FilterInputMessage](../../../../docs/framework/wpf/app-development/filterinputmessage.md).</span></span>  
  
 <span data-ttu-id="fa3a5-118">承载的应用程序注册后的原始输入设备 （人机接口设备） 返回的集接收原始输入的消息[GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md)。</span><span class="sxs-lookup"><span data-stu-id="fa3a5-118">The hosted application receives raw input messages by registering with the set of raw input devices (Human Interface Devices) returned by [GetRawInputDevices](../../../../docs/framework/wpf/app-development/getrawinputdevices.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa3a5-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="fa3a5-119">See Also</span></span>  
 [<span data-ttu-id="fa3a5-120">WM_INPUT 通知</span><span class="sxs-lookup"><span data-stu-id="fa3a5-120">WM_INPUT Notification</span></span>](https://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputmessages/wm_input.asp)
