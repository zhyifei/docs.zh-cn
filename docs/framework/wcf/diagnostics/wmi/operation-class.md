---
title: Operation 类
ms.date: 03/30/2017
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
ms.openlocfilehash: 16de8b25594896349ea546d3def52dd256fe5c70
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "49371584"
---
# <a name="operation-class"></a><span data-ttu-id="b12f9-102">Operation 类</span><span class="sxs-lookup"><span data-stu-id="b12f9-102">Operation class</span></span>
<span data-ttu-id="b12f9-103">操作</span><span class="sxs-lookup"><span data-stu-id="b12f9-103">Operation</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b12f9-104">语法</span><span class="sxs-lookup"><span data-stu-id="b12f9-104">Syntax</span></span>  
  
```csharp
class Operation  
{  
  string Action;  
  boolean AsyncPattern;  
  Behavior Behaviors[];  
  boolean IsCallback;  
  boolean IsInitiating;  
  boolean IsOneWay;  
  boolean IsTerminating;  
  string MethodSignature;  
  string Name;  
  string ParameterTypes[];  
  string ReplyAction;  
  string ReturnType;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b12f9-105">方法</span><span class="sxs-lookup"><span data-stu-id="b12f9-105">Methods</span></span>  
 <span data-ttu-id="b12f9-106">Operation 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="b12f9-106">The Operation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b12f9-107">属性</span><span class="sxs-lookup"><span data-stu-id="b12f9-107">Properties</span></span>  
 <span data-ttu-id="b12f9-108">Operation 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="b12f9-108">The Operation class has the following properties:</span></span>  
  
### <a name="action"></a><span data-ttu-id="b12f9-109">操作</span><span class="sxs-lookup"><span data-stu-id="b12f9-109">Action</span></span>  
 <span data-ttu-id="b12f9-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="b12f9-110">Data type: string</span></span>  
  
 <span data-ttu-id="b12f9-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b12f9-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b12f9-112">请求消息的 WS-Addressing 操作。</span><span class="sxs-lookup"><span data-stu-id="b12f9-112">The WS-Addressing action of the request message.</span></span>  
  
### <a name="asyncpattern"></a><span data-ttu-id="b12f9-113">AsyncPattern</span><span class="sxs-lookup"><span data-stu-id="b12f9-113">AsyncPattern</span></span>  
 <span data-ttu-id="b12f9-114">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="b12f9-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="b12f9-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b12f9-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b12f9-116">指示操作以异步方式使用实现`Begin`[左/右尖括号] 和`End`[左/右尖括号] 方法对服务协定中的。</span><span class="sxs-lookup"><span data-stu-id="b12f9-116">Indicates that an operation is implemented asynchronously using a `Begin`[open/close angle brackets] and `End`[open/close angle brackets] method pair in a service contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="b12f9-117">行为</span><span class="sxs-lookup"><span data-stu-id="b12f9-117">Behaviors</span></span>  
 <span data-ttu-id="b12f9-118">数据类型：Behavior array</span><span class="sxs-lookup"><span data-stu-id="b12f9-118">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="b12f9-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b12f9-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b12f9-120">与此操作关联的行为。</span><span class="sxs-lookup"><span data-stu-id="b12f9-120">The behaviors associated with this operation.</span></span>  
  
### <a name="iscallback"></a><span data-ttu-id="b12f9-121">IsCallback</span><span class="sxs-lookup"><span data-stu-id="b12f9-121">IsCallback</span></span>  
 <span data-ttu-id="b12f9-122">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="b12f9-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="b12f9-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b12f9-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b12f9-124">如果操作为回调操作，则为 True。</span><span class="sxs-lookup"><span data-stu-id="b12f9-124">True when the operation is a callback operation.</span></span>  
  
### <a name="isinitiating"></a><span data-ttu-id="b12f9-125">IsInitiating</span><span class="sxs-lookup"><span data-stu-id="b12f9-125">IsInitiating</span></span>  
 <span data-ttu-id="b12f9-126">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="b12f9-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="b12f9-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b12f9-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b12f9-128">指示方法是否实现了可以启动服务器上的某个会话的操作。</span><span class="sxs-lookup"><span data-stu-id="b12f9-128">Indicates whether the method implements an operation that can initiate a session on the server.</span></span>  
  
### <a name="isoneway"></a><span data-ttu-id="b12f9-129">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="b12f9-129">IsOneWay</span></span>  
 <span data-ttu-id="b12f9-130">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="b12f9-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="b12f9-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b12f9-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b12f9-132">指示操作是否返回答复消息。</span><span class="sxs-lookup"><span data-stu-id="b12f9-132">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="isterminating"></a><span data-ttu-id="b12f9-133">IsTerminating</span><span class="sxs-lookup"><span data-stu-id="b12f9-133">IsTerminating</span></span>  
 <span data-ttu-id="b12f9-134">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="b12f9-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="b12f9-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b12f9-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b12f9-136">指示操作是否返回答复消息。</span><span class="sxs-lookup"><span data-stu-id="b12f9-136">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="methodsignature"></a><span data-ttu-id="b12f9-137">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="b12f9-137">MethodSignature</span></span>  
 <span data-ttu-id="b12f9-138">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="b12f9-138">Data type: string</span></span>  
  
 <span data-ttu-id="b12f9-139">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b12f9-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b12f9-140">操作的方法签名。</span><span class="sxs-lookup"><span data-stu-id="b12f9-140">The method signature of the operation.</span></span>  
  
### <a name="name"></a><span data-ttu-id="b12f9-141">name</span><span class="sxs-lookup"><span data-stu-id="b12f9-141">Name</span></span>  
 <span data-ttu-id="b12f9-142">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="b12f9-142">Data type: string</span></span>  
  
 <span data-ttu-id="b12f9-143">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b12f9-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b12f9-144">操作的名称。</span><span class="sxs-lookup"><span data-stu-id="b12f9-144">The name of the operation.</span></span>  
  
### <a name="parametertypes"></a><span data-ttu-id="b12f9-145">ParameterTypes</span><span class="sxs-lookup"><span data-stu-id="b12f9-145">ParameterTypes</span></span>  
 <span data-ttu-id="b12f9-146">数据类型：String array</span><span class="sxs-lookup"><span data-stu-id="b12f9-146">Data type: string array</span></span>  
  
 <span data-ttu-id="b12f9-147">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b12f9-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b12f9-148">操作的参数类型。</span><span class="sxs-lookup"><span data-stu-id="b12f9-148">The types of the parameters of the operation.</span></span>  
  
### <a name="replyaction"></a><span data-ttu-id="b12f9-149">ReplyAction</span><span class="sxs-lookup"><span data-stu-id="b12f9-149">ReplyAction</span></span>  
 <span data-ttu-id="b12f9-150">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="b12f9-150">Data type: string</span></span>  
  
 <span data-ttu-id="b12f9-151">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b12f9-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b12f9-152">用于该操作答复消息的 SOAP 操作的值。</span><span class="sxs-lookup"><span data-stu-id="b12f9-152">The value of the SOAP action for the reply message of the operation.</span></span>  
  
### <a name="returntype"></a><span data-ttu-id="b12f9-153">ReturnType</span><span class="sxs-lookup"><span data-stu-id="b12f9-153">ReturnType</span></span>  
 <span data-ttu-id="b12f9-154">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="b12f9-154">Data type: string</span></span>  
  
 <span data-ttu-id="b12f9-155">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b12f9-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b12f9-156">操作的返回类型。</span><span class="sxs-lookup"><span data-stu-id="b12f9-156">The return type of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b12f9-157">要求</span><span class="sxs-lookup"><span data-stu-id="b12f9-157">Requirements</span></span>  
  
|<span data-ttu-id="b12f9-158">MOF</span><span class="sxs-lookup"><span data-stu-id="b12f9-158">MOF</span></span>|<span data-ttu-id="b12f9-159">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="b12f9-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b12f9-160">命名空间</span><span class="sxs-lookup"><span data-stu-id="b12f9-160">Namespace</span></span>|<span data-ttu-id="b12f9-161">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="b12f9-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b12f9-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="b12f9-162">See Also</span></span>  
 <xref:System.ServiceModel.Description.OperationDescription>
