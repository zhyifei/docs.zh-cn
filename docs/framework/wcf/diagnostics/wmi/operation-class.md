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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 739f8309e7a01eeecf921b50fcde24417fbbc515
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="operation-class"></a><span data-ttu-id="3a69a-102">Operation 类</span><span class="sxs-lookup"><span data-stu-id="3a69a-102">Operation class</span></span>
<span data-ttu-id="3a69a-103">操作</span><span class="sxs-lookup"><span data-stu-id="3a69a-103">Operation</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a69a-104">语法</span><span class="sxs-lookup"><span data-stu-id="3a69a-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="3a69a-105">方法</span><span class="sxs-lookup"><span data-stu-id="3a69a-105">Methods</span></span>  
 <span data-ttu-id="3a69a-106">Operation 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="3a69a-106">The Operation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3a69a-107">属性</span><span class="sxs-lookup"><span data-stu-id="3a69a-107">Properties</span></span>  
 <span data-ttu-id="3a69a-108">Operation 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="3a69a-108">The Operation class has the following properties:</span></span>  
  
### <a name="action"></a><span data-ttu-id="3a69a-109">操作</span><span class="sxs-lookup"><span data-stu-id="3a69a-109">Action</span></span>  
 <span data-ttu-id="3a69a-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="3a69a-110">Data type: string</span></span>  
  
 <span data-ttu-id="3a69a-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3a69a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3a69a-112">请求消息的 WS-Addressing 操作。</span><span class="sxs-lookup"><span data-stu-id="3a69a-112">The WS-Addressing action of the request message.</span></span>  
  
### <a name="asyncpattern"></a><span data-ttu-id="3a69a-113">AsyncPattern</span><span class="sxs-lookup"><span data-stu-id="3a69a-113">AsyncPattern</span></span>  
 <span data-ttu-id="3a69a-114">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="3a69a-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="3a69a-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3a69a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3a69a-116">指示使用以异步方式实现某个操作`Begin`[左/右尖括号] 和`End`[左/右尖括号] 方法对服务协定中的。</span><span class="sxs-lookup"><span data-stu-id="3a69a-116">Indicates that an operation is implemented asynchronously using a `Begin`[open/close angle brackets] and `End`[open/close angle brackets] method pair in a service contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="3a69a-117">行为</span><span class="sxs-lookup"><span data-stu-id="3a69a-117">Behaviors</span></span>  
 <span data-ttu-id="3a69a-118">数据类型：Behavior array</span><span class="sxs-lookup"><span data-stu-id="3a69a-118">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="3a69a-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3a69a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3a69a-120">与此操作关联的行为。</span><span class="sxs-lookup"><span data-stu-id="3a69a-120">The behaviors associated with this operation.</span></span>  
  
### <a name="iscallback"></a><span data-ttu-id="3a69a-121">IsCallback</span><span class="sxs-lookup"><span data-stu-id="3a69a-121">IsCallback</span></span>  
 <span data-ttu-id="3a69a-122">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="3a69a-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="3a69a-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3a69a-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3a69a-124">如果操作为回调操作，则为 True。</span><span class="sxs-lookup"><span data-stu-id="3a69a-124">True when the operation is a callback operation.</span></span>  
  
### <a name="isinitiating"></a><span data-ttu-id="3a69a-125">IsInitiating</span><span class="sxs-lookup"><span data-stu-id="3a69a-125">IsInitiating</span></span>  
 <span data-ttu-id="3a69a-126">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="3a69a-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="3a69a-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3a69a-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3a69a-128">指示方法是否实现了可以启动服务器上的某个会话的操作。</span><span class="sxs-lookup"><span data-stu-id="3a69a-128">Indicates whether the method implements an operation that can initiate a session on the server.</span></span>  
  
### <a name="isoneway"></a><span data-ttu-id="3a69a-129">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="3a69a-129">IsOneWay</span></span>  
 <span data-ttu-id="3a69a-130">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="3a69a-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="3a69a-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3a69a-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3a69a-132">指示操作是否返回答复消息。</span><span class="sxs-lookup"><span data-stu-id="3a69a-132">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="isterminating"></a><span data-ttu-id="3a69a-133">IsTerminating</span><span class="sxs-lookup"><span data-stu-id="3a69a-133">IsTerminating</span></span>  
 <span data-ttu-id="3a69a-134">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="3a69a-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="3a69a-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3a69a-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3a69a-136">指示操作是否返回答复消息。</span><span class="sxs-lookup"><span data-stu-id="3a69a-136">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="methodsignature"></a><span data-ttu-id="3a69a-137">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="3a69a-137">MethodSignature</span></span>  
 <span data-ttu-id="3a69a-138">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="3a69a-138">Data type: string</span></span>  
  
 <span data-ttu-id="3a69a-139">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3a69a-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3a69a-140">操作的方法签名。</span><span class="sxs-lookup"><span data-stu-id="3a69a-140">The method signature of the operation.</span></span>  
  
### <a name="name"></a><span data-ttu-id="3a69a-141">名称</span><span class="sxs-lookup"><span data-stu-id="3a69a-141">Name</span></span>  
 <span data-ttu-id="3a69a-142">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="3a69a-142">Data type: string</span></span>  
  
 <span data-ttu-id="3a69a-143">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3a69a-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3a69a-144">操作的名称。</span><span class="sxs-lookup"><span data-stu-id="3a69a-144">The name of the operation.</span></span>  
  
### <a name="parametertypes"></a><span data-ttu-id="3a69a-145">ParameterTypes</span><span class="sxs-lookup"><span data-stu-id="3a69a-145">ParameterTypes</span></span>  
 <span data-ttu-id="3a69a-146">数据类型：String array</span><span class="sxs-lookup"><span data-stu-id="3a69a-146">Data type: string array</span></span>  
  
 <span data-ttu-id="3a69a-147">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3a69a-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3a69a-148">操作的参数类型。</span><span class="sxs-lookup"><span data-stu-id="3a69a-148">The types of the parameters of the operation.</span></span>  
  
### <a name="replyaction"></a><span data-ttu-id="3a69a-149">ReplyAction</span><span class="sxs-lookup"><span data-stu-id="3a69a-149">ReplyAction</span></span>  
 <span data-ttu-id="3a69a-150">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="3a69a-150">Data type: string</span></span>  
  
 <span data-ttu-id="3a69a-151">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3a69a-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3a69a-152">用于该操作答复消息的 SOAP 操作的值。</span><span class="sxs-lookup"><span data-stu-id="3a69a-152">The value of the SOAP action for the reply message of the operation.</span></span>  
  
### <a name="returntype"></a><span data-ttu-id="3a69a-153">ReturnType</span><span class="sxs-lookup"><span data-stu-id="3a69a-153">ReturnType</span></span>  
 <span data-ttu-id="3a69a-154">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="3a69a-154">Data type: string</span></span>  
  
 <span data-ttu-id="3a69a-155">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3a69a-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3a69a-156">操作的返回类型。</span><span class="sxs-lookup"><span data-stu-id="3a69a-156">The return type of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a69a-157">要求</span><span class="sxs-lookup"><span data-stu-id="3a69a-157">Requirements</span></span>  
  
|<span data-ttu-id="3a69a-158">MOF</span><span class="sxs-lookup"><span data-stu-id="3a69a-158">MOF</span></span>|<span data-ttu-id="3a69a-159">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="3a69a-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3a69a-160">命名空间</span><span class="sxs-lookup"><span data-stu-id="3a69a-160">Namespace</span></span>|<span data-ttu-id="3a69a-161">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="3a69a-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3a69a-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a69a-162">See Also</span></span>  
 <xref:System.ServiceModel.Description.OperationDescription>
