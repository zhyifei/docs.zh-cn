---
title: "Operation 类"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 54566bc452baa2e02cef7d8d13d29fcd5864c95c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="operation-class"></a><span data-ttu-id="0e282-102">Operation 类</span><span class="sxs-lookup"><span data-stu-id="0e282-102">Operation class</span></span>
<span data-ttu-id="0e282-103">操作</span><span class="sxs-lookup"><span data-stu-id="0e282-103">Operation</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e282-104">语法</span><span class="sxs-lookup"><span data-stu-id="0e282-104">Syntax</span></span>  
  
```  
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
  
## <a name="methods"></a><span data-ttu-id="0e282-105">方法</span><span class="sxs-lookup"><span data-stu-id="0e282-105">Methods</span></span>  
 <span data-ttu-id="0e282-106">Operation 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="0e282-106">The Operation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0e282-107">属性</span><span class="sxs-lookup"><span data-stu-id="0e282-107">Properties</span></span>  
 <span data-ttu-id="0e282-108">Operation 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="0e282-108">The Operation class has the following properties:</span></span>  
  
### <a name="action"></a><span data-ttu-id="0e282-109">操作</span><span class="sxs-lookup"><span data-stu-id="0e282-109">Action</span></span>  
 <span data-ttu-id="0e282-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="0e282-110">Data type: string</span></span>  
  
 <span data-ttu-id="0e282-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0e282-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0e282-112">请求消息的 WS-Addressing 操作。</span><span class="sxs-lookup"><span data-stu-id="0e282-112">The WS-Addressing action of the request message.</span></span>  
  
### <a name="asyncpattern"></a><span data-ttu-id="0e282-113">AsyncPattern</span><span class="sxs-lookup"><span data-stu-id="0e282-113">AsyncPattern</span></span>  
 <span data-ttu-id="0e282-114">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="0e282-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="0e282-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0e282-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0e282-116">指示使用以异步方式实现某个操作`Begin`[左/右尖括号] 和`End`[左/右尖括号] 方法对服务协定中的。</span><span class="sxs-lookup"><span data-stu-id="0e282-116">Indicates that an operation is implemented asynchronously using a `Begin`[open/close angle brackets] and `End`[open/close angle brackets] method pair in a service contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="0e282-117">行为</span><span class="sxs-lookup"><span data-stu-id="0e282-117">Behaviors</span></span>  
 <span data-ttu-id="0e282-118">数据类型：Behavior array</span><span class="sxs-lookup"><span data-stu-id="0e282-118">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="0e282-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0e282-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0e282-120">与此操作关联的行为。</span><span class="sxs-lookup"><span data-stu-id="0e282-120">The behaviors associated with this operation.</span></span>  
  
### <a name="iscallback"></a><span data-ttu-id="0e282-121">IsCallback</span><span class="sxs-lookup"><span data-stu-id="0e282-121">IsCallback</span></span>  
 <span data-ttu-id="0e282-122">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="0e282-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="0e282-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0e282-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0e282-124">如果操作为回调操作，则为 True。</span><span class="sxs-lookup"><span data-stu-id="0e282-124">True when the operation is a callback operation.</span></span>  
  
### <a name="isinitiating"></a><span data-ttu-id="0e282-125">IsInitiating</span><span class="sxs-lookup"><span data-stu-id="0e282-125">IsInitiating</span></span>  
 <span data-ttu-id="0e282-126">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="0e282-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="0e282-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0e282-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0e282-128">指示方法是否实现了可以启动服务器上的某个会话的操作。</span><span class="sxs-lookup"><span data-stu-id="0e282-128">Indicates whether the method implements an operation that can initiate a session on the server.</span></span>  
  
### <a name="isoneway"></a><span data-ttu-id="0e282-129">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="0e282-129">IsOneWay</span></span>  
 <span data-ttu-id="0e282-130">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="0e282-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="0e282-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0e282-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0e282-132">指示操作是否返回答复消息。</span><span class="sxs-lookup"><span data-stu-id="0e282-132">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="isterminating"></a><span data-ttu-id="0e282-133">IsTerminating</span><span class="sxs-lookup"><span data-stu-id="0e282-133">IsTerminating</span></span>  
 <span data-ttu-id="0e282-134">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="0e282-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="0e282-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0e282-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0e282-136">指示操作是否返回答复消息。</span><span class="sxs-lookup"><span data-stu-id="0e282-136">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="methodsignature"></a><span data-ttu-id="0e282-137">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="0e282-137">MethodSignature</span></span>  
 <span data-ttu-id="0e282-138">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="0e282-138">Data type: string</span></span>  
  
 <span data-ttu-id="0e282-139">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0e282-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0e282-140">操作的方法签名。</span><span class="sxs-lookup"><span data-stu-id="0e282-140">The method signature of the operation.</span></span>  
  
### <a name="name"></a><span data-ttu-id="0e282-141">name</span><span class="sxs-lookup"><span data-stu-id="0e282-141">Name</span></span>  
 <span data-ttu-id="0e282-142">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="0e282-142">Data type: string</span></span>  
  
 <span data-ttu-id="0e282-143">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0e282-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0e282-144">操作的名称。</span><span class="sxs-lookup"><span data-stu-id="0e282-144">The name of the operation.</span></span>  
  
### <a name="parametertypes"></a><span data-ttu-id="0e282-145">ParameterTypes</span><span class="sxs-lookup"><span data-stu-id="0e282-145">ParameterTypes</span></span>  
 <span data-ttu-id="0e282-146">数据类型：String array</span><span class="sxs-lookup"><span data-stu-id="0e282-146">Data type: string array</span></span>  
  
 <span data-ttu-id="0e282-147">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0e282-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0e282-148">操作的参数类型。</span><span class="sxs-lookup"><span data-stu-id="0e282-148">The types of the parameters of the operation.</span></span>  
  
### <a name="replyaction"></a><span data-ttu-id="0e282-149">ReplyAction</span><span class="sxs-lookup"><span data-stu-id="0e282-149">ReplyAction</span></span>  
 <span data-ttu-id="0e282-150">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="0e282-150">Data type: string</span></span>  
  
 <span data-ttu-id="0e282-151">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0e282-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0e282-152">用于该操作答复消息的 SOAP 操作的值。</span><span class="sxs-lookup"><span data-stu-id="0e282-152">The value of the SOAP action for the reply message of the operation.</span></span>  
  
### <a name="returntype"></a><span data-ttu-id="0e282-153">ReturnType</span><span class="sxs-lookup"><span data-stu-id="0e282-153">ReturnType</span></span>  
 <span data-ttu-id="0e282-154">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="0e282-154">Data type: string</span></span>  
  
 <span data-ttu-id="0e282-155">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0e282-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0e282-156">操作的返回类型。</span><span class="sxs-lookup"><span data-stu-id="0e282-156">The return type of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e282-157">惠?</span><span class="sxs-lookup"><span data-stu-id="0e282-157">Requirements</span></span>  
  
|<span data-ttu-id="0e282-158">MOF</span><span class="sxs-lookup"><span data-stu-id="0e282-158">MOF</span></span>|<span data-ttu-id="0e282-159">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="0e282-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="0e282-160">命名空间</span><span class="sxs-lookup"><span data-stu-id="0e282-160">Namespace</span></span>|<span data-ttu-id="0e282-161">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="0e282-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0e282-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e282-162">See Also</span></span>  
 <xref:System.ServiceModel.Description.OperationDescription>
