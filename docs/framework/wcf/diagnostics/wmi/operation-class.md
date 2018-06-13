---
title: Operation 类
ms.date: 03/30/2017
ms.assetid: b19d1496-ef06-4d0c-b2ae-e728ec00cca0
ms.openlocfilehash: d9256915afe9fdb8e4c91d186131fe41a7094c56
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33487563"
---
# <a name="operation-class"></a><span data-ttu-id="60faf-102">Operation 类</span><span class="sxs-lookup"><span data-stu-id="60faf-102">Operation class</span></span>
<span data-ttu-id="60faf-103">操作</span><span class="sxs-lookup"><span data-stu-id="60faf-103">Operation</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60faf-104">语法</span><span class="sxs-lookup"><span data-stu-id="60faf-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="60faf-105">方法</span><span class="sxs-lookup"><span data-stu-id="60faf-105">Methods</span></span>  
 <span data-ttu-id="60faf-106">Operation 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="60faf-106">The Operation class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="60faf-107">属性</span><span class="sxs-lookup"><span data-stu-id="60faf-107">Properties</span></span>  
 <span data-ttu-id="60faf-108">Operation 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="60faf-108">The Operation class has the following properties:</span></span>  
  
### <a name="action"></a><span data-ttu-id="60faf-109">操作</span><span class="sxs-lookup"><span data-stu-id="60faf-109">Action</span></span>  
 <span data-ttu-id="60faf-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="60faf-110">Data type: string</span></span>  
  
 <span data-ttu-id="60faf-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="60faf-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="60faf-112">请求消息的 WS-Addressing 操作。</span><span class="sxs-lookup"><span data-stu-id="60faf-112">The WS-Addressing action of the request message.</span></span>  
  
### <a name="asyncpattern"></a><span data-ttu-id="60faf-113">AsyncPattern</span><span class="sxs-lookup"><span data-stu-id="60faf-113">AsyncPattern</span></span>  
 <span data-ttu-id="60faf-114">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="60faf-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="60faf-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="60faf-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="60faf-116">指示使用以异步方式实现某个操作`Begin`[左/右尖括号] 和`End`[左/右尖括号] 方法对服务协定中的。</span><span class="sxs-lookup"><span data-stu-id="60faf-116">Indicates that an operation is implemented asynchronously using a `Begin`[open/close angle brackets] and `End`[open/close angle brackets] method pair in a service contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="60faf-117">行为</span><span class="sxs-lookup"><span data-stu-id="60faf-117">Behaviors</span></span>  
 <span data-ttu-id="60faf-118">数据类型：Behavior array</span><span class="sxs-lookup"><span data-stu-id="60faf-118">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="60faf-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="60faf-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="60faf-120">与此操作关联的行为。</span><span class="sxs-lookup"><span data-stu-id="60faf-120">The behaviors associated with this operation.</span></span>  
  
### <a name="iscallback"></a><span data-ttu-id="60faf-121">IsCallback</span><span class="sxs-lookup"><span data-stu-id="60faf-121">IsCallback</span></span>  
 <span data-ttu-id="60faf-122">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="60faf-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="60faf-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="60faf-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="60faf-124">如果操作为回调操作，则为 True。</span><span class="sxs-lookup"><span data-stu-id="60faf-124">True when the operation is a callback operation.</span></span>  
  
### <a name="isinitiating"></a><span data-ttu-id="60faf-125">IsInitiating</span><span class="sxs-lookup"><span data-stu-id="60faf-125">IsInitiating</span></span>  
 <span data-ttu-id="60faf-126">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="60faf-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="60faf-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="60faf-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="60faf-128">指示方法是否实现了可以启动服务器上的某个会话的操作。</span><span class="sxs-lookup"><span data-stu-id="60faf-128">Indicates whether the method implements an operation that can initiate a session on the server.</span></span>  
  
### <a name="isoneway"></a><span data-ttu-id="60faf-129">IsOneWay</span><span class="sxs-lookup"><span data-stu-id="60faf-129">IsOneWay</span></span>  
 <span data-ttu-id="60faf-130">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="60faf-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="60faf-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="60faf-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="60faf-132">指示操作是否返回答复消息。</span><span class="sxs-lookup"><span data-stu-id="60faf-132">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="isterminating"></a><span data-ttu-id="60faf-133">IsTerminating</span><span class="sxs-lookup"><span data-stu-id="60faf-133">IsTerminating</span></span>  
 <span data-ttu-id="60faf-134">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="60faf-134">Data type: boolean</span></span>  
  
 <span data-ttu-id="60faf-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="60faf-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="60faf-136">指示操作是否返回答复消息。</span><span class="sxs-lookup"><span data-stu-id="60faf-136">Indicates whether an operation returns a reply message.</span></span>  
  
### <a name="methodsignature"></a><span data-ttu-id="60faf-137">MethodSignature</span><span class="sxs-lookup"><span data-stu-id="60faf-137">MethodSignature</span></span>  
 <span data-ttu-id="60faf-138">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="60faf-138">Data type: string</span></span>  
  
 <span data-ttu-id="60faf-139">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="60faf-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="60faf-140">操作的方法签名。</span><span class="sxs-lookup"><span data-stu-id="60faf-140">The method signature of the operation.</span></span>  
  
### <a name="name"></a><span data-ttu-id="60faf-141">名称</span><span class="sxs-lookup"><span data-stu-id="60faf-141">Name</span></span>  
 <span data-ttu-id="60faf-142">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="60faf-142">Data type: string</span></span>  
  
 <span data-ttu-id="60faf-143">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="60faf-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="60faf-144">操作的名称。</span><span class="sxs-lookup"><span data-stu-id="60faf-144">The name of the operation.</span></span>  
  
### <a name="parametertypes"></a><span data-ttu-id="60faf-145">ParameterTypes</span><span class="sxs-lookup"><span data-stu-id="60faf-145">ParameterTypes</span></span>  
 <span data-ttu-id="60faf-146">数据类型：String array</span><span class="sxs-lookup"><span data-stu-id="60faf-146">Data type: string array</span></span>  
  
 <span data-ttu-id="60faf-147">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="60faf-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="60faf-148">操作的参数类型。</span><span class="sxs-lookup"><span data-stu-id="60faf-148">The types of the parameters of the operation.</span></span>  
  
### <a name="replyaction"></a><span data-ttu-id="60faf-149">ReplyAction</span><span class="sxs-lookup"><span data-stu-id="60faf-149">ReplyAction</span></span>  
 <span data-ttu-id="60faf-150">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="60faf-150">Data type: string</span></span>  
  
 <span data-ttu-id="60faf-151">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="60faf-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="60faf-152">用于该操作答复消息的 SOAP 操作的值。</span><span class="sxs-lookup"><span data-stu-id="60faf-152">The value of the SOAP action for the reply message of the operation.</span></span>  
  
### <a name="returntype"></a><span data-ttu-id="60faf-153">ReturnType</span><span class="sxs-lookup"><span data-stu-id="60faf-153">ReturnType</span></span>  
 <span data-ttu-id="60faf-154">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="60faf-154">Data type: string</span></span>  
  
 <span data-ttu-id="60faf-155">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="60faf-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="60faf-156">操作的返回类型。</span><span class="sxs-lookup"><span data-stu-id="60faf-156">The return type of the operation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60faf-157">要求</span><span class="sxs-lookup"><span data-stu-id="60faf-157">Requirements</span></span>  
  
|<span data-ttu-id="60faf-158">MOF</span><span class="sxs-lookup"><span data-stu-id="60faf-158">MOF</span></span>|<span data-ttu-id="60faf-159">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="60faf-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="60faf-160">命名空间</span><span class="sxs-lookup"><span data-stu-id="60faf-160">Namespace</span></span>|<span data-ttu-id="60faf-161">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="60faf-161">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="60faf-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="60faf-162">See Also</span></span>  
 <xref:System.ServiceModel.Description.OperationDescription>
