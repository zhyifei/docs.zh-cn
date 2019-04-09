---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: 51555e3357b8c33a53261c4894d97798b0a05656
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59102929"
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="75a09-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="75a09-102">ServiceAuthorizationBehavior</span></span>
<span data-ttu-id="75a09-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="75a09-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75a09-104">语法</span><span class="sxs-lookup"><span data-stu-id="75a09-104">Syntax</span></span>  
  
```csharp
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="75a09-105">方法</span><span class="sxs-lookup"><span data-stu-id="75a09-105">Methods</span></span>  
 <span data-ttu-id="75a09-106">ServiceAuthorizationBehavior 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="75a09-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="75a09-107">属性</span><span class="sxs-lookup"><span data-stu-id="75a09-107">Properties</span></span>  
 <span data-ttu-id="75a09-108">ServiceAuthorizationBehavior 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="75a09-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="75a09-109">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="75a09-109">ImpersonateCallerForAllOperations</span></span>  
 <span data-ttu-id="75a09-110">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="75a09-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="75a09-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="75a09-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="75a09-112">一个值，控制服务是否尝试使用传入消息所提供的凭据进行模拟。</span><span class="sxs-lookup"><span data-stu-id="75a09-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="75a09-113">PrincipalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="75a09-113">PrincipalPermissionMode</span></span>  
 <span data-ttu-id="75a09-114">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="75a09-114">Data type: string</span></span>  
  
 <span data-ttu-id="75a09-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="75a09-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="75a09-116">用于在服务器上执行操作的主体。</span><span class="sxs-lookup"><span data-stu-id="75a09-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="75a09-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="75a09-117">RoleProvider</span></span>  
 <span data-ttu-id="75a09-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="75a09-118">Data type: string</span></span>  
  
 <span data-ttu-id="75a09-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="75a09-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="75a09-120">ASP.NET 角色提供程序的名称。</span><span class="sxs-lookup"><span data-stu-id="75a09-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="75a09-121">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="75a09-121">ServiceAuthorizationManager</span></span>  
 <span data-ttu-id="75a09-122">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="75a09-122">Data type: string</span></span>  
  
 <span data-ttu-id="75a09-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="75a09-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="75a09-124">用于自定义授权的授权管理器。</span><span class="sxs-lookup"><span data-stu-id="75a09-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75a09-125">要求</span><span class="sxs-lookup"><span data-stu-id="75a09-125">Requirements</span></span>  
  
|<span data-ttu-id="75a09-126">MOF</span><span class="sxs-lookup"><span data-stu-id="75a09-126">MOF</span></span>|<span data-ttu-id="75a09-127">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="75a09-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="75a09-128">命名空间</span><span class="sxs-lookup"><span data-stu-id="75a09-128">Namespace</span></span>|<span data-ttu-id="75a09-129">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="75a09-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="75a09-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="75a09-130">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
