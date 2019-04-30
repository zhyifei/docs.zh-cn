---
title: MsmqTransportBindingElement
ms.date: 03/30/2017
ms.assetid: 1c89f073-9ed3-4025-a8c5-13535a0f526b
ms.openlocfilehash: 706cec5c414197ebabda7939728b95be32582e0f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963301"
---
# <a name="msmqtransportbindingelement"></a><span data-ttu-id="f9cdf-102">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="f9cdf-102">MsmqTransportBindingElement</span></span>
<span data-ttu-id="f9cdf-103">MsmqTransportBindingElement</span><span class="sxs-lookup"><span data-stu-id="f9cdf-103">MsmqTransportBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9cdf-104">语法</span><span class="sxs-lookup"><span data-stu-id="f9cdf-104">Syntax</span></span>  
  
```csharp
class MsmqTransportBindingElement : MsmqBindingElementBase  
{  
  sint32 MaxPoolSize;  
  string QueueTransferProtocol;  
  boolean UseActiveDirectory;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f9cdf-105">方法</span><span class="sxs-lookup"><span data-stu-id="f9cdf-105">Methods</span></span>  
 <span data-ttu-id="f9cdf-106">MsmqTransportBindingElement 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-106">The MsmqTransportBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f9cdf-107">属性</span><span class="sxs-lookup"><span data-stu-id="f9cdf-107">Properties</span></span>  
 <span data-ttu-id="f9cdf-108">MsmqTransportBindingElement 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="f9cdf-108">The MsmqTransportBindingElement class has the following properties:</span></span>  
  
### <a name="maxpoolsize"></a><span data-ttu-id="f9cdf-109">MaxPoolSize</span><span class="sxs-lookup"><span data-stu-id="f9cdf-109">MaxPoolSize</span></span>  
 <span data-ttu-id="f9cdf-110">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="f9cdf-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="f9cdf-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="f9cdf-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f9cdf-112">包含内部 MSMQ 消息对象的池的最大大小。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-112">The maximum size of the pool that contains internal MSMQ message objects.</span></span>  
  
### <a name="queuetransferprotocol"></a><span data-ttu-id="f9cdf-113">QueueTransferProtocol</span><span class="sxs-lookup"><span data-stu-id="f9cdf-113">QueueTransferProtocol</span></span>  
 <span data-ttu-id="f9cdf-114">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="f9cdf-114">Data type: string</span></span>  
  
 <span data-ttu-id="f9cdf-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="f9cdf-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f9cdf-116">一个枚举值，指示此绑定使用的排队通信通道传输。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-116">An enumeration value that indicates the queued communication channel transport that this binding uses.</span></span>  
  
### <a name="useactivedirectory"></a><span data-ttu-id="f9cdf-117">UseActiveDirectory</span><span class="sxs-lookup"><span data-stu-id="f9cdf-117">UseActiveDirectory</span></span>  
 <span data-ttu-id="f9cdf-118">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="f9cdf-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="f9cdf-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="f9cdf-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f9cdf-120">返回一个布尔值，该值指示是否应该使用 Active Directory 来转换队列地址。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-120">Returns a Boolean value that indicates whether queue addresses should be converted using Active Directory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9cdf-121">要求</span><span class="sxs-lookup"><span data-stu-id="f9cdf-121">Requirements</span></span>  
  
|<span data-ttu-id="f9cdf-122">MOF</span><span class="sxs-lookup"><span data-stu-id="f9cdf-122">MOF</span></span>|<span data-ttu-id="f9cdf-123">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="f9cdf-123">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f9cdf-124">命名空间</span><span class="sxs-lookup"><span data-stu-id="f9cdf-124">Namespace</span></span>|<span data-ttu-id="f9cdf-125">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="f9cdf-125">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f9cdf-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="f9cdf-126">See also</span></span>

- <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
