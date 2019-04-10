---
title: OneWayBindingElement
ms.date: 03/30/2017
ms.assetid: 5c7e17c3-39b9-4214-ae08-9e6141734305
ms.openlocfilehash: 016ff823eb2c84a9f54c0763edadef1224e31517
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168735"
---
# <a name="onewaybindingelement"></a><span data-ttu-id="b9e87-102">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="b9e87-102">OneWayBindingElement</span></span>
<span data-ttu-id="b9e87-103">OneWayBindingElement</span><span class="sxs-lookup"><span data-stu-id="b9e87-103">OneWayBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9e87-104">语法</span><span class="sxs-lookup"><span data-stu-id="b9e87-104">Syntax</span></span>  
  
```csharp
class OneWayBindingElement : BindingElement  
{  
  ChannelPoolSettings ChannelPoolSettings;  
  sint32 MaxAcceptedChannels;  
  boolean PacketRoutable;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b9e87-105">方法</span><span class="sxs-lookup"><span data-stu-id="b9e87-105">Methods</span></span>  
 <span data-ttu-id="b9e87-106">OneWayBindingElement 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="b9e87-106">The OneWayBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b9e87-107">属性</span><span class="sxs-lookup"><span data-stu-id="b9e87-107">Properties</span></span>  
 <span data-ttu-id="b9e87-108">OneWayBindingElement 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="b9e87-108">The OneWayBindingElement class has the following properties:</span></span>  
  
### <a name="channelpoolsettings"></a><span data-ttu-id="b9e87-109">ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="b9e87-109">ChannelPoolSettings</span></span>  
 <span data-ttu-id="b9e87-110">数据类型：ChannelPoolSettings</span><span class="sxs-lookup"><span data-stu-id="b9e87-110">Data type: ChannelPoolSettings</span></span>  
  
 <span data-ttu-id="b9e87-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b9e87-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b9e87-112">通道池设置。</span><span class="sxs-lookup"><span data-stu-id="b9e87-112">The channel pool settings.</span></span>  
  
### <a name="maxacceptedchannels"></a><span data-ttu-id="b9e87-113">MaxAcceptedChannels</span><span class="sxs-lookup"><span data-stu-id="b9e87-113">MaxAcceptedChannels</span></span>  
 <span data-ttu-id="b9e87-114">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="b9e87-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="b9e87-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b9e87-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b9e87-116">接受的最大通道数。</span><span class="sxs-lookup"><span data-stu-id="b9e87-116">The maximum number of accepted channels.</span></span>  
  
### <a name="packetroutable"></a><span data-ttu-id="b9e87-117">PacketRoutable</span><span class="sxs-lookup"><span data-stu-id="b9e87-117">PacketRoutable</span></span>  
 <span data-ttu-id="b9e87-118">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="b9e87-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="b9e87-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b9e87-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b9e87-120">一个值，该值指示数据包是否可路由。</span><span class="sxs-lookup"><span data-stu-id="b9e87-120">A value that indicates whether the packet is routable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9e87-121">要求</span><span class="sxs-lookup"><span data-stu-id="b9e87-121">Requirements</span></span>  
  
|<span data-ttu-id="b9e87-122">MOF</span><span class="sxs-lookup"><span data-stu-id="b9e87-122">MOF</span></span>|<span data-ttu-id="b9e87-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="b9e87-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b9e87-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="b9e87-124">Namespace</span></span>|<span data-ttu-id="b9e87-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="b9e87-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b9e87-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9e87-126">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
