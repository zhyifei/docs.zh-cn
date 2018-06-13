---
title: OperationBehaviorAttribute
ms.date: 03/30/2017
ms.assetid: 8c9b0755-9e83-411f-bdcb-61a586022797
ms.openlocfilehash: 4f731d146885265d9f956c182f1bebdba5db924b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486866"
---
# <a name="operationbehaviorattribute"></a><span data-ttu-id="a4056-102">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="a4056-102">OperationBehaviorAttribute</span></span>
<span data-ttu-id="a4056-103">OperationBehaviorAttribute</span><span class="sxs-lookup"><span data-stu-id="a4056-103">OperationBehaviorAttribute</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4056-104">语法</span><span class="sxs-lookup"><span data-stu-id="a4056-104">Syntax</span></span>  
  
```  
class OperationBehaviorAttribute : Behavior  
{  
  boolean AutoDisposeParameters;  
  string Impersonation;  
  string ReleaseInstanceMode;  
  boolean TransactionAutoComplete;  
  boolean TransactionScopeRequired;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="a4056-105">方法</span><span class="sxs-lookup"><span data-stu-id="a4056-105">Methods</span></span>  
 <span data-ttu-id="a4056-106">OperationBehaviorAttribute 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="a4056-106">The OperationBehaviorAttribute class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="a4056-107">属性</span><span class="sxs-lookup"><span data-stu-id="a4056-107">Properties</span></span>  
 <span data-ttu-id="a4056-108">OperationBehaviorAttribute 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="a4056-108">The OperationBehaviorAttribute class has the following properties:</span></span>  
  
### <a name="autodisposeparameters"></a><span data-ttu-id="a4056-109">AutoDisposeParameters</span><span class="sxs-lookup"><span data-stu-id="a4056-109">AutoDisposeParameters</span></span>  
 <span data-ttu-id="a4056-110">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="a4056-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="a4056-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="a4056-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a4056-112">参数自动释放功能的状态。</span><span class="sxs-lookup"><span data-stu-id="a4056-112">The state of the auto-dispose feature for parameters.</span></span>  
  
### <a name="impersonation"></a><span data-ttu-id="a4056-113">Impersonation</span><span class="sxs-lookup"><span data-stu-id="a4056-113">Impersonation</span></span>  
 <span data-ttu-id="a4056-114">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="a4056-114">Data type: string</span></span>  
  
 <span data-ttu-id="a4056-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="a4056-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a4056-116">指示操作支持的调用方模拟级别。</span><span class="sxs-lookup"><span data-stu-id="a4056-116">Indicates the level of caller impersonation that the operation supports.</span></span>  
  
### <a name="releaseinstancemode"></a><span data-ttu-id="a4056-117">ReleaseInstanceMode</span><span class="sxs-lookup"><span data-stu-id="a4056-117">ReleaseInstanceMode</span></span>  
 <span data-ttu-id="a4056-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="a4056-118">Data type: string</span></span>  
  
 <span data-ttu-id="a4056-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="a4056-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a4056-120">指示操作调用过程中何时回收对象。</span><span class="sxs-lookup"><span data-stu-id="a4056-120">Indicates when in the course of an operation invocation to recycle the object.</span></span>  
  
### <a name="transactionautocomplete"></a><span data-ttu-id="a4056-121">TransactionAutoComplete</span><span class="sxs-lookup"><span data-stu-id="a4056-121">TransactionAutoComplete</span></span>  
 <span data-ttu-id="a4056-122">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="a4056-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="a4056-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="a4056-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a4056-124">指示在未发生未处理的异常的情况下是否自动提交当前事务。</span><span class="sxs-lookup"><span data-stu-id="a4056-124">Indicates whether to automatically commit the current transaction if no unhandled exceptions occur.</span></span>  
  
### <a name="transactionscoperequired"></a><span data-ttu-id="a4056-125">TransactionScopeRequired</span><span class="sxs-lookup"><span data-stu-id="a4056-125">TransactionScopeRequired</span></span>  
 <span data-ttu-id="a4056-126">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="a4056-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="a4056-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="a4056-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="a4056-128">指示操作是否需要事务处理。</span><span class="sxs-lookup"><span data-stu-id="a4056-128">Indicates whether the operation requires a transaction.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4056-129">要求</span><span class="sxs-lookup"><span data-stu-id="a4056-129">Requirements</span></span>  
  
|<span data-ttu-id="a4056-130">MOF</span><span class="sxs-lookup"><span data-stu-id="a4056-130">MOF</span></span>|<span data-ttu-id="a4056-131">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="a4056-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="a4056-132">命名空间</span><span class="sxs-lookup"><span data-stu-id="a4056-132">Namespace</span></span>|<span data-ttu-id="a4056-133">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="a4056-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="a4056-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4056-134">See Also</span></span>  
 <xref:System.ServiceModel.OperationBehaviorAttribute>
