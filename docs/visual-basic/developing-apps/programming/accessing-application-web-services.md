---
title: 访问应用程序 Web 服务 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Web services [Visual Basic], My.WebServices object
- My.WebServices object
- applications [Visual Basic], Web services
ms.assetid: 8ad5405b-e771-42b1-82d3-ce97af2cea9e
ms.openlocfilehash: b1d5a2166ace2ea16e1764139133457439675876
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583729"
---
# <a name="accessing-application-web-services-visual-basic"></a><span data-ttu-id="60bf6-102">访问应用程序 Web 服务 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="60bf6-102">Accessing Application Web Services (Visual Basic)</span></span>
<span data-ttu-id="60bf6-103">`My.WebServices` 对象提供当前项目所引用的每个 Web 服务的实例。</span><span class="sxs-lookup"><span data-stu-id="60bf6-103">The `My.WebServices` object provides an instance of each Web service referenced by the current project.</span></span> <span data-ttu-id="60bf6-104">按需实例化每个实例。</span><span class="sxs-lookup"><span data-stu-id="60bf6-104">Each instance is instantiated on demand.</span></span> <span data-ttu-id="60bf6-105">可以通过 `My.WebServices` 对象的属性访问这些 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="60bf6-105">You can access these Web services through the properties of the `My.WebServices` object.</span></span> <span data-ttu-id="60bf6-106">该属性的名称与该属性所访问的 Web 服务的名称相同。</span><span class="sxs-lookup"><span data-stu-id="60bf6-106">The name of the property is the same as the name of the Web service that the property accesses.</span></span> <span data-ttu-id="60bf6-107">任何自 <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> 继承的类均为 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="60bf6-107">Any class that inherits from <xref:System.Web.Services.Protocols.SoapHttpClientProtocol> is a Web service.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="60bf6-108">任务</span><span class="sxs-lookup"><span data-stu-id="60bf6-108">Tasks</span></span>  
 <span data-ttu-id="60bf6-109">下表列出了访问应用程序所引用的 Web 服务的可能方法。</span><span class="sxs-lookup"><span data-stu-id="60bf6-109">The following table lists possible ways to access Web services referenced by an application.</span></span>  
  
|<span data-ttu-id="60bf6-110">到</span><span class="sxs-lookup"><span data-stu-id="60bf6-110">To</span></span>|<span data-ttu-id="60bf6-111">查看</span><span class="sxs-lookup"><span data-stu-id="60bf6-111">See</span></span>|  
|---|---|   
|<span data-ttu-id="60bf6-112">调用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="60bf6-112">Call a Web service</span></span>|[<span data-ttu-id="60bf6-113">My.WebServices 对象</span><span class="sxs-lookup"><span data-stu-id="60bf6-113">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)|  
|<span data-ttu-id="60bf6-114">以异步方式调用 Web 服务，并在事件完成时处理该事件</span><span class="sxs-lookup"><span data-stu-id="60bf6-114">Call a Web service asynchronously and handle an event when it completes</span></span>|[<span data-ttu-id="60bf6-115">如何：异步调用 Web 服务</span><span class="sxs-lookup"><span data-stu-id="60bf6-115">How to: Call a Web Service Asynchronously</span></span>](../../../visual-basic/developing-apps/programming/how-to-call-a-web-service-asynchronously.md)|  
  
## <a name="see-also"></a><span data-ttu-id="60bf6-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="60bf6-116">See Also</span></span>  
 [<span data-ttu-id="60bf6-117">My.WebServices 对象</span><span class="sxs-lookup"><span data-stu-id="60bf6-117">My.WebServices Object</span></span>](../../../visual-basic/language-reference/objects/my-webservices-object.md)
