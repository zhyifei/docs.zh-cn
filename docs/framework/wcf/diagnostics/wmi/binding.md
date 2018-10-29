---
title: Binding2
ms.date: 03/30/2017
ms.assetid: 09511c6c-5749-4bb0-874e-0f0be36bfe04
ms.openlocfilehash: 84e304f3dedcbd785d6238e6cb5eb142c288b995
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2018
ms.locfileid: "50198884"
---
# <a name="binding"></a><span data-ttu-id="c4f25-102">绑定</span><span class="sxs-lookup"><span data-stu-id="c4f25-102">Binding</span></span>
<span data-ttu-id="c4f25-103">wmi Binding</span><span class="sxs-lookup"><span data-stu-id="c4f25-103">wmi Binding</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4f25-104">语法</span><span class="sxs-lookup"><span data-stu-id="c4f25-104">Syntax</span></span>  
  
```csharp
class Binding  
{  
  BindingElement BindingElements[];  
  datetime CloseTimeout;  
  string Name;  
  string Namespace;  
  datetime OpenTimeout;  
  datetime ReceiveTimeout;  
  string Scheme;  
  datetime SendTimeout;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c4f25-105">方法</span><span class="sxs-lookup"><span data-stu-id="c4f25-105">Methods</span></span>  
 <span data-ttu-id="c4f25-106">Binding 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="c4f25-106">The Binding class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c4f25-107">属性</span><span class="sxs-lookup"><span data-stu-id="c4f25-107">Properties</span></span>  
 <span data-ttu-id="c4f25-108">Binding 类具有以下属性。</span><span class="sxs-lookup"><span data-stu-id="c4f25-108">The Binding class has the following properties.</span></span>  
  
### <a name="bindingelements"></a><span data-ttu-id="c4f25-109">BindingElements</span><span class="sxs-lookup"><span data-stu-id="c4f25-109">BindingElements</span></span>  
 <span data-ttu-id="c4f25-110">数据类型：BindingElement 数组</span><span class="sxs-lookup"><span data-stu-id="c4f25-110">Data type: BindingElement array</span></span>  
  
 <span data-ttu-id="c4f25-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="c4f25-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c4f25-112">由绑定实现的绑定元素的集合。</span><span class="sxs-lookup"><span data-stu-id="c4f25-112">The collection of binding elements implemented by the binding.</span></span>  
  
### <a name="closetimeout"></a><span data-ttu-id="c4f25-113">CloseTimeout</span><span class="sxs-lookup"><span data-stu-id="c4f25-113">CloseTimeout</span></span>  
 <span data-ttu-id="c4f25-114">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="c4f25-114">Data type: datetime</span></span>  
  
 <span data-ttu-id="c4f25-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="c4f25-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c4f25-116">为完成关闭操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="c4f25-116">The interval of time provided for a close operation to complete.</span></span>  
  
### <a name="name"></a><span data-ttu-id="c4f25-117">name</span><span class="sxs-lookup"><span data-stu-id="c4f25-117">Name</span></span>  
 <span data-ttu-id="c4f25-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="c4f25-118">Data type: string</span></span>  
  
 <span data-ttu-id="c4f25-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="c4f25-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c4f25-120">绑定的名称。</span><span class="sxs-lookup"><span data-stu-id="c4f25-120">The name of the binding.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="c4f25-121">命名空间</span><span class="sxs-lookup"><span data-stu-id="c4f25-121">Namespace</span></span>  
 <span data-ttu-id="c4f25-122">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="c4f25-122">Data type: string</span></span>  
  
 <span data-ttu-id="c4f25-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="c4f25-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c4f25-124">绑定的 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="c4f25-124">The XML namespace of the binding.</span></span>  
  
### <a name="opentimeout"></a><span data-ttu-id="c4f25-125">OpenTimeout</span><span class="sxs-lookup"><span data-stu-id="c4f25-125">OpenTimeout</span></span>  
 <span data-ttu-id="c4f25-126">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="c4f25-126">Data type: datetime</span></span>  
  
 <span data-ttu-id="c4f25-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="c4f25-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c4f25-128">为完成打开操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="c4f25-128">The interval of time provided for an open operation to complete.</span></span>  
  
### <a name="receivetimeout"></a><span data-ttu-id="c4f25-129">ReceiveTimeout</span><span class="sxs-lookup"><span data-stu-id="c4f25-129">ReceiveTimeout</span></span>  
 <span data-ttu-id="c4f25-130">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="c4f25-130">Data type: datetime</span></span>  
  
 <span data-ttu-id="c4f25-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="c4f25-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c4f25-132">为完成接收操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="c4f25-132">The interval of time provided for a receive operation to complete.</span></span>  
  
### <a name="scheme"></a><span data-ttu-id="c4f25-133">方案</span><span class="sxs-lookup"><span data-stu-id="c4f25-133">Scheme</span></span>  
 <span data-ttu-id="c4f25-134">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="c4f25-134">Data type: string</span></span>  
  
 <span data-ttu-id="c4f25-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="c4f25-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c4f25-136">绑定建立的通道和侦听器工厂所使用的 URI 传输方案。</span><span class="sxs-lookup"><span data-stu-id="c4f25-136">The URI transport scheme that is used by the channel and listener factories that are built by the binding.</span></span>  
  
### <a name="sendtimeout"></a><span data-ttu-id="c4f25-137">SendTimeout</span><span class="sxs-lookup"><span data-stu-id="c4f25-137">SendTimeout</span></span>  
 <span data-ttu-id="c4f25-138">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="c4f25-138">Data type: datetime</span></span>  
  
 <span data-ttu-id="c4f25-139">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="c4f25-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c4f25-140">为完成发送操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="c4f25-140">The interval of time provided for a send operation to complete.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4f25-141">要求</span><span class="sxs-lookup"><span data-stu-id="c4f25-141">Requirements</span></span>  
  
|<span data-ttu-id="c4f25-142">MOF</span><span class="sxs-lookup"><span data-stu-id="c4f25-142">MOF</span></span>|<span data-ttu-id="c4f25-143">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="c4f25-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c4f25-144">命名空间</span><span class="sxs-lookup"><span data-stu-id="c4f25-144">Namespace</span></span>|<span data-ttu-id="c4f25-145">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="c4f25-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c4f25-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4f25-146">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>
