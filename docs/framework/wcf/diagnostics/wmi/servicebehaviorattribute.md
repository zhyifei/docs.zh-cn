---
title: ServiceBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 5faa266f-587f-4e03-828d-1c7dd5acfe65
ms.openlocfilehash: b6221e93f10b87a368bd594932a8c36ae14df8f3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59206871"
---
# <a name="servicebehaviorattribute"></a><span data-ttu-id="1f6a5-102">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="1f6a5-102">ServiceBehaviorAttribute</span></span>
<span data-ttu-id="1f6a5-103">ServiceBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="1f6a5-103">ServiceBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f6a5-104">语法</span><span class="sxs-lookup"><span data-stu-id="1f6a5-104">Syntax</span></span>  
  
```csharp
class ServiceBehaviorAttribute : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  string ConfigurationName;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  string InstanceContextMode;  
  sint32 MaxItemsInObjectGraph;  
  string Name;  
  string Namespace;  
  boolean ReleaseServiceInstanceOnTransactionComplete;  
  boolean TransactionAutoCompleteOnSessionClose;  
  string TransactionIsolationLevel;  
  datetime TransactionTimeout;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1f6a5-105">方法</span><span class="sxs-lookup"><span data-stu-id="1f6a5-105">Methods</span></span>  
 <span data-ttu-id="1f6a5-106">ServiceBehaviorAttribute 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="1f6a5-106">The ServiceBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1f6a5-107">属性</span><span class="sxs-lookup"><span data-stu-id="1f6a5-107">Properties</span></span>  
 <span data-ttu-id="1f6a5-108">ServiceBehaviorAttribute 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="1f6a5-108">The ServiceBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="1f6a5-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="1f6a5-109">AutomaticSessionShutdown</span></span>  
 <span data-ttu-id="1f6a5-110">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="1f6a5-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="1f6a5-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="1f6a5-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f6a5-112">指示在客户端关闭输出会话时是否自动关闭会话。</span><span class="sxs-lookup"><span data-stu-id="1f6a5-112">Indicates whether to automatically close a session when a client closes an output session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="1f6a5-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="1f6a5-113">ConcurrencyMode</span></span>  
 <span data-ttu-id="1f6a5-114">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="1f6a5-114">Data type: string</span></span>  
<span data-ttu-id="1f6a5-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="1f6a5-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f6a5-116">指示服务是支持单线程、多线程还是支持可重入调用。</span><span class="sxs-lookup"><span data-stu-id="1f6a5-116">Indicates whether a service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="1f6a5-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="1f6a5-117">ConfigurationName</span></span>  
 <span data-ttu-id="1f6a5-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="1f6a5-118">Data type: string</span></span>  
  
 <span data-ttu-id="1f6a5-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="1f6a5-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f6a5-120">服务配置的名称。</span><span class="sxs-lookup"><span data-stu-id="1f6a5-120">The name of the service configuration.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="1f6a5-121">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="1f6a5-121">IgnoreExtensionDataObject</span></span>  
 <span data-ttu-id="1f6a5-122">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="1f6a5-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="1f6a5-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="1f6a5-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f6a5-124">指定是否要将未知序列化数据发送到网络上。</span><span class="sxs-lookup"><span data-stu-id="1f6a5-124">Specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="1f6a5-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="1f6a5-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="1f6a5-126">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="1f6a5-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="1f6a5-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="1f6a5-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f6a5-128">指定是否在返回给客户端的 SOAP 错误详细信息中包含托管异常信息以供调试。</span><span class="sxs-lookup"><span data-stu-id="1f6a5-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
### <a name="instancecontextmode"></a><span data-ttu-id="1f6a5-129">InstanceContextMode</span><span class="sxs-lookup"><span data-stu-id="1f6a5-129">InstanceContextMode</span></span>  
 <span data-ttu-id="1f6a5-130">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="1f6a5-130">Data type: string</span></span>  
  
 <span data-ttu-id="1f6a5-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="1f6a5-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f6a5-132">指定何时创建新服务对象。</span><span class="sxs-lookup"><span data-stu-id="1f6a5-132">Specifies when a new service object is created.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="1f6a5-133">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="1f6a5-133">MaxItemsInObjectGraph</span></span>  
 <span data-ttu-id="1f6a5-134">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="1f6a5-134">Data type: sint32</span></span>  
  
 <span data-ttu-id="1f6a5-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="1f6a5-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f6a5-136">序列化对象中允许的最大项数。</span><span class="sxs-lookup"><span data-stu-id="1f6a5-136">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="name"></a><span data-ttu-id="1f6a5-137">名称</span><span class="sxs-lookup"><span data-stu-id="1f6a5-137">Name</span></span>  
 <span data-ttu-id="1f6a5-138">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="1f6a5-138">Data type: string</span></span>  
  
 <span data-ttu-id="1f6a5-139">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="1f6a5-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f6a5-140">WSDL 中服务的名称属性。</span><span class="sxs-lookup"><span data-stu-id="1f6a5-140">The name attribute of the service in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="1f6a5-141">命名空间</span><span class="sxs-lookup"><span data-stu-id="1f6a5-141">Namespace</span></span>  
 <span data-ttu-id="1f6a5-142">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="1f6a5-142">Data type: string</span></span>  
  
 <span data-ttu-id="1f6a5-143">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="1f6a5-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f6a5-144">WSDL 中服务的目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="1f6a5-144">The target namespace of the service in WSDL.</span></span>  
  
### <a name="releaseserviceinstanceontransactioncomplete"></a><span data-ttu-id="1f6a5-145">ReleaseServiceInstanceOnTransactionComplete</span><span class="sxs-lookup"><span data-stu-id="1f6a5-145">ReleaseServiceInstanceOnTransactionComplete</span></span>  
 <span data-ttu-id="1f6a5-146">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="1f6a5-146">Data type: boolean</span></span>  
  
 <span data-ttu-id="1f6a5-147">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="1f6a5-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f6a5-148">指定当前事务完成后，是否回收服务对象。</span><span class="sxs-lookup"><span data-stu-id="1f6a5-148">Specifies whether the service object is recycled when the current transaction completes.</span></span>  
  
### <a name="transactionautocompleteonsessionclose"></a><span data-ttu-id="1f6a5-149">TransactionAutoCompleteOnSessionClose</span><span class="sxs-lookup"><span data-stu-id="1f6a5-149">TransactionAutoCompleteOnSessionClose</span></span>  
 <span data-ttu-id="1f6a5-150">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="1f6a5-150">Data type: boolean</span></span>  
  
 <span data-ttu-id="1f6a5-151">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="1f6a5-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f6a5-152">指定当前会话关闭时，挂起的事务是否已完成。</span><span class="sxs-lookup"><span data-stu-id="1f6a5-152">Specifies whether pending transactions are completed when the current session closes.</span></span>  
  
### <a name="transactionisolationlevel"></a><span data-ttu-id="1f6a5-153">TransactionIsolationLevel</span><span class="sxs-lookup"><span data-stu-id="1f6a5-153">TransactionIsolationLevel</span></span>  
 <span data-ttu-id="1f6a5-154">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="1f6a5-154">Data type: string</span></span>  
  
 <span data-ttu-id="1f6a5-155">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="1f6a5-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f6a5-156">指定事务的隔离级别。</span><span class="sxs-lookup"><span data-stu-id="1f6a5-156">Specifies the transaction isolation level.</span></span>  
  
### <a name="transactiontimeout"></a><span data-ttu-id="1f6a5-157">TransactionTimeout</span><span class="sxs-lookup"><span data-stu-id="1f6a5-157">TransactionTimeout</span></span>  
 <span data-ttu-id="1f6a5-158">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="1f6a5-158">Data type: datetime</span></span>  
  
 <span data-ttu-id="1f6a5-159">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="1f6a5-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f6a5-160">事务必须在此期间完成的时间段。</span><span class="sxs-lookup"><span data-stu-id="1f6a5-160">The period within which a transaction must complete.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="1f6a5-161">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="1f6a5-161">UseSynchronizationContext</span></span>  
 <span data-ttu-id="1f6a5-162">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="1f6a5-162">Data type: boolean</span></span>  
  
 <span data-ttu-id="1f6a5-163">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="1f6a5-163">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f6a5-164">指定是否使用当前同步上下文来选择线程执行。</span><span class="sxs-lookup"><span data-stu-id="1f6a5-164">Specifies whether to use the current synchronization context to choose the thread execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="1f6a5-165">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="1f6a5-165">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="1f6a5-166">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="1f6a5-166">Data type: boolean</span></span>  
  
 <span data-ttu-id="1f6a5-167">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="1f6a5-167">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1f6a5-168">指定系统或应用程序是否强制执行 SOAP MustUnderstand 标头处理。</span><span class="sxs-lookup"><span data-stu-id="1f6a5-168">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f6a5-169">要求</span><span class="sxs-lookup"><span data-stu-id="1f6a5-169">Requirements</span></span>  
  
|<span data-ttu-id="1f6a5-170">MOF</span><span class="sxs-lookup"><span data-stu-id="1f6a5-170">MOF</span></span>|<span data-ttu-id="1f6a5-171">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="1f6a5-171">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1f6a5-172">命名空间</span><span class="sxs-lookup"><span data-stu-id="1f6a5-172">Namespace</span></span>|<span data-ttu-id="1f6a5-173">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="1f6a5-173">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1f6a5-174">请参阅</span><span class="sxs-lookup"><span data-stu-id="1f6a5-174">See also</span></span>

- <xref:System.ServiceModel.ServiceBehaviorAttribute>
