---
title: ServiceAuthorizationBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: eb02a02557a88bf53ca1a8e5b30fe66d6995e545
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="b905d-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="b905d-102">ServiceAuthorizationBehavior</span></span>
<span data-ttu-id="b905d-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="b905d-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b905d-104">语法</span><span class="sxs-lookup"><span data-stu-id="b905d-104">Syntax</span></span>  
  
```  
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b905d-105">方法</span><span class="sxs-lookup"><span data-stu-id="b905d-105">Methods</span></span>  
 <span data-ttu-id="b905d-106">ServiceAuthorizationBehavior 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="b905d-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b905d-107">属性</span><span class="sxs-lookup"><span data-stu-id="b905d-107">Properties</span></span>  
 <span data-ttu-id="b905d-108">ServiceAuthorizationBehavior 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="b905d-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="b905d-109">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="b905d-109">ImpersonateCallerForAllOperations</span></span>  
 <span data-ttu-id="b905d-110">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="b905d-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="b905d-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b905d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b905d-112">一个值，控制服务是否尝试使用传入消息所提供的凭据进行模拟。</span><span class="sxs-lookup"><span data-stu-id="b905d-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="b905d-113">PrincipalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="b905d-113">PrincipalPermissionMode</span></span>  
 <span data-ttu-id="b905d-114">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="b905d-114">Data type: string</span></span>  
  
 <span data-ttu-id="b905d-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b905d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b905d-116">用于在服务器上执行操作的主体。</span><span class="sxs-lookup"><span data-stu-id="b905d-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="b905d-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="b905d-117">RoleProvider</span></span>  
 <span data-ttu-id="b905d-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="b905d-118">Data type: string</span></span>  
  
 <span data-ttu-id="b905d-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b905d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b905d-120">ASP.NET 角色提供程序的名称。</span><span class="sxs-lookup"><span data-stu-id="b905d-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="b905d-121">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="b905d-121">ServiceAuthorizationManager</span></span>  
 <span data-ttu-id="b905d-122">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="b905d-122">Data type: string</span></span>  
  
 <span data-ttu-id="b905d-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="b905d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b905d-124">用于自定义授权的授权管理器。</span><span class="sxs-lookup"><span data-stu-id="b905d-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b905d-125">要求</span><span class="sxs-lookup"><span data-stu-id="b905d-125">Requirements</span></span>  
  
|<span data-ttu-id="b905d-126">MOF</span><span class="sxs-lookup"><span data-stu-id="b905d-126">MOF</span></span>|<span data-ttu-id="b905d-127">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="b905d-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b905d-128">命名空间</span><span class="sxs-lookup"><span data-stu-id="b905d-128">Namespace</span></span>|<span data-ttu-id="b905d-129">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="b905d-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b905d-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b905d-130">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
