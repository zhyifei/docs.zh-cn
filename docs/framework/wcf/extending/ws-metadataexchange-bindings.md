---
title: WS-MetadataExchange 绑定
ms.date: 03/30/2017
ms.assetid: 10f8de5d-b81d-4ea7-b37e-7f2c00c39714
ms.openlocfilehash: 384e5bb05ba4263f245f6901b84e2388ea19bd73
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33488619"
---
# <a name="ws-metadataexchange-bindings"></a><span data-ttu-id="33958-102">WS-MetadataExchange 绑定</span><span class="sxs-lookup"><span data-stu-id="33958-102">WS-MetadataExchange Bindings</span></span>
<span data-ttu-id="33958-103">本主题说明如何为各种传输构造默认的元数据交换绑定。</span><span class="sxs-lookup"><span data-stu-id="33958-103">This topic describes how the default metadata exchange bindings are constructed for various transports.</span></span>  
  
## <a name="the-default-bindings"></a><span data-ttu-id="33958-104">默认绑定</span><span class="sxs-lookup"><span data-stu-id="33958-104">The Default Bindings</span></span>  
  
|<span data-ttu-id="33958-105">默认绑定名称</span><span class="sxs-lookup"><span data-stu-id="33958-105">Default Binding Name</span></span>|<span data-ttu-id="33958-106">绑定的构造方式</span><span class="sxs-lookup"><span data-stu-id="33958-106">How the binding is constructed</span></span>|  
|--------------------------|------------------------------------|  
|<span data-ttu-id="33958-107">MexHttpBinding</span><span class="sxs-lookup"><span data-stu-id="33958-107">MexHttpBinding</span></span>|<span data-ttu-id="33958-108">一个禁用传输级安全性的 <xref:System.ServiceModel.WSHttpBinding>。</span><span class="sxs-lookup"><span data-stu-id="33958-108">A <xref:System.ServiceModel.WSHttpBinding> with transport-level security disabled.</span></span>|  
|<span data-ttu-id="33958-109">MexHttpsBinding</span><span class="sxs-lookup"><span data-stu-id="33958-109">MexHttpsBinding</span></span>|<span data-ttu-id="33958-110">一个支持传输级安全性的 <xref:System.ServiceModel.WSHttpBinding>。</span><span class="sxs-lookup"><span data-stu-id="33958-110">A <xref:System.ServiceModel.WSHttpBinding> that supports transport-level security.</span></span>|  
|<span data-ttu-id="33958-111">MexNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="33958-111">MexNamedPipeBinding</span></span>|<span data-ttu-id="33958-112">一个 <xref:System.ServiceModel.Channels.CustomBinding>，它具有使用默认值的 <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="33958-112">A  <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement> using the default values.</span></span>|  
|<span data-ttu-id="33958-113">MexTcpBinding</span><span class="sxs-lookup"><span data-stu-id="33958-113">MexTcpBinding</span></span>|<span data-ttu-id="33958-114">一个 <xref:System.ServiceModel.Channels.CustomBinding>，它具有使用默认值的 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="33958-114">A <xref:System.ServiceModel.Channels.CustomBinding> with a <xref:System.ServiceModel.Channels.TcpTransportBindingElement> using default values.</span></span>|
