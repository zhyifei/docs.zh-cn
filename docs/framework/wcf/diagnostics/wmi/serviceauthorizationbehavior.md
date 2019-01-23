---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: 58eb2a9fd9017aaf9966644180936f5871e086d1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54613891"
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="1ece6-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="1ece6-102">ServiceAuthorizationBehavior</span></span>
<span data-ttu-id="1ece6-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="1ece6-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ece6-104">语法</span><span class="sxs-lookup"><span data-stu-id="1ece6-104">Syntax</span></span>  
  
```csharp
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="1ece6-105">方法</span><span class="sxs-lookup"><span data-stu-id="1ece6-105">Methods</span></span>  
 <span data-ttu-id="1ece6-106">ServiceAuthorizationBehavior 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="1ece6-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="1ece6-107">Properties</span><span class="sxs-lookup"><span data-stu-id="1ece6-107">Properties</span></span>  
 <span data-ttu-id="1ece6-108">ServiceAuthorizationBehavior 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="1ece6-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="1ece6-109">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="1ece6-109">ImpersonateCallerForAllOperations</span></span>  
 <span data-ttu-id="1ece6-110">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="1ece6-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="1ece6-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="1ece6-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1ece6-112">一个值，控制服务是否尝试使用传入消息所提供的凭据进行模拟。</span><span class="sxs-lookup"><span data-stu-id="1ece6-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="1ece6-113">PrincipalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="1ece6-113">PrincipalPermissionMode</span></span>  
 <span data-ttu-id="1ece6-114">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="1ece6-114">Data type: string</span></span>  
  
 <span data-ttu-id="1ece6-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="1ece6-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1ece6-116">用于在服务器上执行操作的主体。</span><span class="sxs-lookup"><span data-stu-id="1ece6-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="1ece6-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="1ece6-117">RoleProvider</span></span>  
 <span data-ttu-id="1ece6-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="1ece6-118">Data type: string</span></span>  
  
 <span data-ttu-id="1ece6-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="1ece6-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1ece6-120">ASP.NET 角色提供程序的名称。</span><span class="sxs-lookup"><span data-stu-id="1ece6-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="1ece6-121">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="1ece6-121">ServiceAuthorizationManager</span></span>  
 <span data-ttu-id="1ece6-122">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="1ece6-122">Data type: string</span></span>  
  
 <span data-ttu-id="1ece6-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="1ece6-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="1ece6-124">用于自定义授权的授权管理器。</span><span class="sxs-lookup"><span data-stu-id="1ece6-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ece6-125">要求</span><span class="sxs-lookup"><span data-stu-id="1ece6-125">Requirements</span></span>  
  
|<span data-ttu-id="1ece6-126">MOF</span><span class="sxs-lookup"><span data-stu-id="1ece6-126">MOF</span></span>|<span data-ttu-id="1ece6-127">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="1ece6-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="1ece6-128">命名空间</span><span class="sxs-lookup"><span data-stu-id="1ece6-128">Namespace</span></span>|<span data-ttu-id="1ece6-129">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="1ece6-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1ece6-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="1ece6-130">See also</span></span>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
