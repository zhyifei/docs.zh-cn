---
title: MsmqBindingElementBase
ms.date: 03/30/2017
ms.assetid: 210d41ab-a2a4-4d7a-afd2-0916c08a4015
ms.openlocfilehash: 1df4b32feda246a536183a42ac11b113bc4bb259
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59093749"
---
# <a name="msmqbindingelementbase"></a><span data-ttu-id="18daf-102">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="18daf-102">MsmqBindingElementBase</span></span>
<span data-ttu-id="18daf-103">MsmqBindingElementBase</span><span class="sxs-lookup"><span data-stu-id="18daf-103">MsmqBindingElementBase</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18daf-104">语法</span><span class="sxs-lookup"><span data-stu-id="18daf-104">Syntax</span></span>  
  
```csharp  
class MsmqBindingElementBase : TransportBindingElement  
{  
  string CustomDeadLetterQueue;  
  string DeadLetterQueue;  
  boolean Durable;  
  boolean ExactlyOnce;  
  sint32 MaxRetryCycles;  
  string ReceiveErrorHandling;  
  sint32 ReceiveRetryCount;  
  datetime RetryCycleDelay;  
  datetime TimeToLive;  
  boolean UseMsmqTracing;  
  boolean UseSourceJournal;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="18daf-105">方法</span><span class="sxs-lookup"><span data-stu-id="18daf-105">Methods</span></span>  
 <span data-ttu-id="18daf-106">MsmqBindingElementBase 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="18daf-106">The MsmqBindingElementBase class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="18daf-107">属性</span><span class="sxs-lookup"><span data-stu-id="18daf-107">Properties</span></span>  
 <span data-ttu-id="18daf-108">MsmqBindingElementBase 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="18daf-108">The MsmqBindingElementBase class has the following properties:</span></span>  
  
### <a name="customdeadletterqueue"></a><span data-ttu-id="18daf-109">CustomDeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="18daf-109">CustomDeadLetterQueue</span></span>  
 <span data-ttu-id="18daf-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="18daf-110">Data type: string</span></span>  
  
 <span data-ttu-id="18daf-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="18daf-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="18daf-112">一个 URI，其中包含每个应用程序的死信队列位置（用于放置已过期的消息或传输/传递失败的消息的位置）。</span><span class="sxs-lookup"><span data-stu-id="18daf-112">A URI that contains the location of the dead letter queue for each application, where messages that have expired or that have failed transfer or delivery are placed.</span></span>  
  
### <a name="deadletterqueue"></a><span data-ttu-id="18daf-113">DeadLetterQueue</span><span class="sxs-lookup"><span data-stu-id="18daf-113">DeadLetterQueue</span></span>  
 <span data-ttu-id="18daf-114">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="18daf-114">Data type: string</span></span>  
  
 <span data-ttu-id="18daf-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="18daf-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="18daf-116">一个枚举值，指示要使用的死信队列的类型。</span><span class="sxs-lookup"><span data-stu-id="18daf-116">An enumeration value that indicates the type of dead letter queue to use.</span></span>  
  
### <a name="durable"></a><span data-ttu-id="18daf-117">Durable</span><span class="sxs-lookup"><span data-stu-id="18daf-117">Durable</span></span>  
 <span data-ttu-id="18daf-118">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="18daf-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="18daf-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="18daf-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="18daf-120">一个值，指示此绑定处理的消息是持久的还是可变的。</span><span class="sxs-lookup"><span data-stu-id="18daf-120">A value that indicates whether the messages processed by this binding are durable or volatile.</span></span>  
  
### <a name="exactlyonce"></a><span data-ttu-id="18daf-121">ExactlyOnce</span><span class="sxs-lookup"><span data-stu-id="18daf-121">ExactlyOnce</span></span>  
 <span data-ttu-id="18daf-122">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="18daf-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="18daf-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="18daf-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="18daf-124">一个 Boolean 值，指示是否只接收过一次此绑定处理的消息。</span><span class="sxs-lookup"><span data-stu-id="18daf-124">A Boolean value that indicates whether messages processed by this binding are received exactly once.</span></span>  
  
### <a name="maxretrycycles"></a><span data-ttu-id="18daf-125">MaxRetryCycles</span><span class="sxs-lookup"><span data-stu-id="18daf-125">MaxRetryCycles</span></span>  
 <span data-ttu-id="18daf-126">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="18daf-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="18daf-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="18daf-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="18daf-128">尝试向接收应用程序传递消息的最大重试周期数。</span><span class="sxs-lookup"><span data-stu-id="18daf-128">The maximum number of retry cycles to attempt delivery of messages to the receiving application.</span></span>  
  
### <a name="receiveerrorhandling"></a><span data-ttu-id="18daf-129">ReceiveErrorHandling</span><span class="sxs-lookup"><span data-stu-id="18daf-129">ReceiveErrorHandling</span></span>  
 <span data-ttu-id="18daf-130">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="18daf-130">Data type: string</span></span>  
  
 <span data-ttu-id="18daf-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="18daf-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="18daf-132">病毒消息处理设置。</span><span class="sxs-lookup"><span data-stu-id="18daf-132">The settings for poison message handling.</span></span>  
  
### <a name="receiveretrycount"></a><span data-ttu-id="18daf-133">ReceiveRetryCount</span><span class="sxs-lookup"><span data-stu-id="18daf-133">ReceiveRetryCount</span></span>  
 <span data-ttu-id="18daf-134">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="18daf-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="18daf-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="18daf-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="18daf-136">从应用程序队列读取消息的最大立即重试次数。</span><span class="sxs-lookup"><span data-stu-id="18daf-136">The maximum number of immediate retry attempts on a message that is read from the application queue.</span></span>  
  
### <a name="retrycycledelay"></a><span data-ttu-id="18daf-137">RetryCycleDelay</span><span class="sxs-lookup"><span data-stu-id="18daf-137">RetryCycleDelay</span></span>  
 <span data-ttu-id="18daf-138">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="18daf-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="18daf-139">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="18daf-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="18daf-140">一个值，指示尝试传递无法立即传递的消息时，重试周期之间的时间延迟。</span><span class="sxs-lookup"><span data-stu-id="18daf-140">A value that indicates the time delay between retry cycles when attempting to deliver a message that could not be delivered immediately.</span></span>  
  
### <a name="timetolive"></a><span data-ttu-id="18daf-141">TimeToLive</span><span class="sxs-lookup"><span data-stu-id="18daf-141">TimeToLive</span></span>  
 <span data-ttu-id="18daf-142">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="18daf-142">Data type: datetime</span></span>  
  
 <span data-ttu-id="18daf-143">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="18daf-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="18daf-144">时间间隔，指示此绑定所处理的消息在过期之前可以保留在队列中的时间。</span><span class="sxs-lookup"><span data-stu-id="18daf-144">The interval of time that indicates how long the messages processed by this binding can be in the queue before they expire.</span></span>  
  
### <a name="usemsmqtracing"></a><span data-ttu-id="18daf-145">UseMsmqTracing</span><span class="sxs-lookup"><span data-stu-id="18daf-145">UseMsmqTracing</span></span>  
 <span data-ttu-id="18daf-146">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="18daf-146">Data type: boolean</span></span>  
  
 <span data-ttu-id="18daf-147">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="18daf-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="18daf-148">一个 Boolean 值，指示是否应跟踪此绑定处理的消息。</span><span class="sxs-lookup"><span data-stu-id="18daf-148">A Boolean value that indicates whether messages processed by this binding should be traced.</span></span>  
  
### <a name="usesourcejournal"></a><span data-ttu-id="18daf-149">UseSourceJournal</span><span class="sxs-lookup"><span data-stu-id="18daf-149">UseSourceJournal</span></span>  
 <span data-ttu-id="18daf-150">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="18daf-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="18daf-151">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="18daf-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="18daf-152">一个 Boolean 值，指示此绑定所处理的消息副本是否应存储在源日志队列中。</span><span class="sxs-lookup"><span data-stu-id="18daf-152">A Boolean value that indicates whether copies of messages processed by this binding should be stored in the source journal queue.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18daf-153">要求</span><span class="sxs-lookup"><span data-stu-id="18daf-153">Requirements</span></span>  
  
|<span data-ttu-id="18daf-154">MOF</span><span class="sxs-lookup"><span data-stu-id="18daf-154">MOF</span></span>|<span data-ttu-id="18daf-155">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="18daf-155">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="18daf-156">命名空间</span><span class="sxs-lookup"><span data-stu-id="18daf-156">Namespace</span></span>|<span data-ttu-id="18daf-157">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="18daf-157">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="18daf-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="18daf-158">See also</span></span>

- <xref:System.ServiceModel.NetMsmqBinding>
- <xref:System.ServiceModel.MsmqBindingBase>
