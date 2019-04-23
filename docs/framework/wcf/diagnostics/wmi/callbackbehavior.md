---
title: CallbackBehavior
ms.date: 03/30/2017
ms.assetid: 42acd302-2b62-4849-a2d1-a03084343ecd
ms.openlocfilehash: 9d8f4335c304d164daafeb0ad4de5b4e3bba4590
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "59973962"
---
# <a name="callbackbehavior"></a><span data-ttu-id="2c74b-102">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="2c74b-102">CallbackBehavior</span></span>
<span data-ttu-id="2c74b-103">CallbackBehavior</span><span class="sxs-lookup"><span data-stu-id="2c74b-103">CallbackBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c74b-104">语法</span><span class="sxs-lookup"><span data-stu-id="2c74b-104">Syntax</span></span>  
  
```csharp
class CallbackBehavior : Behavior  
{  
  boolean AutomaticSessionShutdown;  
  string ConcurrencyMode;  
  boolean IgnoreExtensionDataObject;  
  boolean IncludeExceptionDetailInFaults;  
  boolean MaxItemsInObjectGraph;  
  boolean UseSynchronizationContext;  
  boolean ValidateMustUnderstand;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="2c74b-105">方法</span><span class="sxs-lookup"><span data-stu-id="2c74b-105">Methods</span></span>  
 <span data-ttu-id="2c74b-106">CallbackBehavior 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="2c74b-106">The CallbackBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="2c74b-107">属性</span><span class="sxs-lookup"><span data-stu-id="2c74b-107">Properties</span></span>  
 <span data-ttu-id="2c74b-108">CallbackBehavior 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="2c74b-108">The CallbackBehavior class has the following properties:</span></span>  
  
### <a name="automaticsessionshutdown"></a><span data-ttu-id="2c74b-109">AutomaticSessionShutdown</span><span class="sxs-lookup"><span data-stu-id="2c74b-109">AutomaticSessionShutdown</span></span>  
 <span data-ttu-id="2c74b-110">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="2c74b-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="2c74b-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="2c74b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2c74b-112">如果为 true，则会话在服务关闭双工会话时自动关闭。</span><span class="sxs-lookup"><span data-stu-id="2c74b-112">When true, the session is automatically closed when a service closes a duplex session.</span></span>  
  
### <a name="concurrencymode"></a><span data-ttu-id="2c74b-113">ConcurrencyMode</span><span class="sxs-lookup"><span data-stu-id="2c74b-113">ConcurrencyMode</span></span>  
 <span data-ttu-id="2c74b-114">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="2c74b-114">Data type: string</span></span>  
<span data-ttu-id="2c74b-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="2c74b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2c74b-116">指定服务是支持一个线程、多个线程还是支持可重入调用。</span><span class="sxs-lookup"><span data-stu-id="2c74b-116">Specifies whether the service supports one thread, multiple threads, or reentrant calls.</span></span>  
  
### <a name="ignoreextensiondataobject"></a><span data-ttu-id="2c74b-117">IgnoreExtensionDataObject</span><span class="sxs-lookup"><span data-stu-id="2c74b-117">IgnoreExtensionDataObject</span></span>  
 <span data-ttu-id="2c74b-118">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="2c74b-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="2c74b-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="2c74b-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2c74b-120">一个值，指定是否将未知序列化数据发送到网络上。</span><span class="sxs-lookup"><span data-stu-id="2c74b-120">A value that specifies whether to send unknown serialization data onto the wire.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="2c74b-121">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="2c74b-121">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="2c74b-122">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="2c74b-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="2c74b-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="2c74b-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2c74b-124">如果启用，则回调异常的详细信息被附加到服务所返回的错误中。</span><span class="sxs-lookup"><span data-stu-id="2c74b-124">When enabled, details about exceptions on the callback are attached to the faults returned to the service.</span></span>  
  
### <a name="maxitemsinobjectgraph"></a><span data-ttu-id="2c74b-125">MaxItemsInObjectGraph</span><span class="sxs-lookup"><span data-stu-id="2c74b-125">MaxItemsInObjectGraph</span></span>  
 <span data-ttu-id="2c74b-126">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="2c74b-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="2c74b-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="2c74b-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2c74b-128">序列化对象中允许的最大项数。</span><span class="sxs-lookup"><span data-stu-id="2c74b-128">The maximum number of items allowed in a serialized object.</span></span>  
  
### <a name="usesynchronizationcontext"></a><span data-ttu-id="2c74b-129">UseSynchronizationContext</span><span class="sxs-lookup"><span data-stu-id="2c74b-129">UseSynchronizationContext</span></span>  
 <span data-ttu-id="2c74b-130">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="2c74b-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="2c74b-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="2c74b-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2c74b-132">指定是否使用当前同步上下文来选择执行的线程。</span><span class="sxs-lookup"><span data-stu-id="2c74b-132">Specifies whether to use the current synchronization context to choose the thread of execution.</span></span>  
  
### <a name="validatemustunderstand"></a><span data-ttu-id="2c74b-133">ValidateMustUnderstand</span><span class="sxs-lookup"><span data-stu-id="2c74b-133">ValidateMustUnderstand</span></span>  
 <span data-ttu-id="2c74b-134">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="2c74b-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="2c74b-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="2c74b-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="2c74b-136">指定系统或应用程序是否强制执行 SOAP MustUnderstand 标头处理。</span><span class="sxs-lookup"><span data-stu-id="2c74b-136">Specifies whether the system or the application enforces SOAP MustUnderstand header processing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c74b-137">要求</span><span class="sxs-lookup"><span data-stu-id="2c74b-137">Requirements</span></span>  
  
|<span data-ttu-id="2c74b-138">MOF</span><span class="sxs-lookup"><span data-stu-id="2c74b-138">MOF</span></span>|<span data-ttu-id="2c74b-139">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="2c74b-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="2c74b-140">命名空间</span><span class="sxs-lookup"><span data-stu-id="2c74b-140">Namespace</span></span>|<span data-ttu-id="2c74b-141">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="2c74b-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2c74b-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c74b-142">See also</span></span>

- <xref:System.ServiceModel.CallbackBehaviorAttribute>
