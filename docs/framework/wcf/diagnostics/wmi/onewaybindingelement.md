---
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: 34220a3651819978f5f597fdc67d54630ec5e059
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50195809"
---
# <a name="onewaybindingelement"></a><span data-ttu-id="108e6-102">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="108e6-102">OneWayBindingElement</span></span>
<span data-ttu-id="108e6-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="108e6-103">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="108e6-104">语法</span><span class="sxs-lookup"><span data-stu-id="108e6-104">Syntax</span></span>  
  
```csharp
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="108e6-105">方法</span><span class="sxs-lookup"><span data-stu-id="108e6-105">Methods</span></span>  
 <span data-ttu-id="108e6-106">OneWayBindingElement 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="108e6-106">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="108e6-107">属性</span><span class="sxs-lookup"><span data-stu-id="108e6-107">Properties</span></span>  
 <span data-ttu-id="108e6-108">OneWayBindingElement 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="108e6-108">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="108e6-109">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="108e6-109">ChannelPoolSettings</span></span>  
 <span data-ttu-id="108e6-110">数据类型：ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="108e6-110">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="108e6-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="108e6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="108e6-112">通道池设置。</span><span class="sxs-lookup"><span data-stu-id="108e6-112">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="108e6-113">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="108e6-113">MaxAcceptedChannels</span></span>  
 <span data-ttu-id="108e6-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="108e6-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="108e6-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="108e6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="108e6-116">接受的最大通道数。</span><span class="sxs-lookup"><span data-stu-id="108e6-116">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="108e6-117">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="108e6-117">PacketRoutable</span></span>  
 <span data-ttu-id="108e6-118">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="108e6-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="108e6-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="108e6-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="108e6-120">一个值，该值指示数据包是否可路由。</span><span class="sxs-lookup"><span data-stu-id="108e6-120">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="108e6-121">要求</span><span class="sxs-lookup"><span data-stu-id="108e6-121">Requirements</span></span>  
  
|<span data-ttu-id="108e6-122">MOF</span><span class="sxs-lookup"><span data-stu-id="108e6-122">MOF</span></span>|<span data-ttu-id="108e6-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="108e6-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="108e6-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="108e6-124">Namespace</span></span>|<span data-ttu-id="108e6-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="108e6-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="108e6-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="108e6-126">See Also</span></span>  
 <xref:System.ServiceModel.Channels.OneWayBindingElement>
