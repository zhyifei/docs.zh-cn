---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 3adc721dd8ad0fb706e172373e5da70fe6032db6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485890"
---
# <a name="servicesecurityauditbehavior"></a><span data-ttu-id="bb240-102">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="bb240-102">ServiceSecurityAuditBehavior</span></span>
<span data-ttu-id="bb240-103">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="bb240-103">ServiceSecurityAuditBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb240-104">语法</span><span class="sxs-lookup"><span data-stu-id="bb240-104">Syntax</span></span>  
  
```  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="bb240-105">方法</span><span class="sxs-lookup"><span data-stu-id="bb240-105">Methods</span></span>  
 <span data-ttu-id="bb240-106">ServiceSecurityAuditBehavior 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="bb240-106">The ServiceSecurityAuditBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bb240-107">属性</span><span class="sxs-lookup"><span data-stu-id="bb240-107">Properties</span></span>  
 <span data-ttu-id="bb240-108">ServiceSecurityAuditBehavior 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="bb240-108">The ServiceSecurityAuditBehavior class has the following properties:</span></span>  
  
### <a name="auditloglocation"></a><span data-ttu-id="bb240-109">AuditLogLocation</span><span class="sxs-lookup"><span data-stu-id="bb240-109">AuditLogLocation</span></span>  
 <span data-ttu-id="bb240-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="bb240-110">Data type: string</span></span>  
  
 <span data-ttu-id="bb240-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="bb240-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bb240-112">审核日志的位置。</span><span class="sxs-lookup"><span data-stu-id="bb240-112">The location of the audit log.</span></span>  
  
### <a name="messageauthenticationauditlevel"></a><span data-ttu-id="bb240-113">MessageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="bb240-113">MessageAuthenticationAuditLevel</span></span>  
 <span data-ttu-id="bb240-114">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="bb240-114">Data type: string</span></span>  
  
 <span data-ttu-id="bb240-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="bb240-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bb240-116">用于记录审核事件的消息身份验证级别的类型。</span><span class="sxs-lookup"><span data-stu-id="bb240-116">The type of message authentication level that is used to log audit events.</span></span>  
  
### <a name="serviceauthorizationauditlevel"></a><span data-ttu-id="bb240-117">ServiceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="bb240-117">ServiceAuthorizationAuditLevel</span></span>  
 <span data-ttu-id="bb240-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="bb240-118">Data type: string</span></span>  
  
 <span data-ttu-id="bb240-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="bb240-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bb240-120">审核日志中记录的授权事件类型。</span><span class="sxs-lookup"><span data-stu-id="bb240-120">The types of authorization events that are recorded in the audit log.</span></span>  
  
### <a name="suppressauditfailure"></a><span data-ttu-id="bb240-121">SuppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="bb240-121">SuppressAuditFailure</span></span>  
 <span data-ttu-id="bb240-122">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="bb240-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="bb240-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="bb240-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bb240-124">一个 boolean 值，指定取消显示审核日志写入失败的行为。</span><span class="sxs-lookup"><span data-stu-id="bb240-124">A boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb240-125">要求</span><span class="sxs-lookup"><span data-stu-id="bb240-125">Requirements</span></span>  
  
|<span data-ttu-id="bb240-126">MOF</span><span class="sxs-lookup"><span data-stu-id="bb240-126">MOF</span></span>|<span data-ttu-id="bb240-127">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="bb240-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bb240-128">命名空间</span><span class="sxs-lookup"><span data-stu-id="bb240-128">Namespace</span></span>|<span data-ttu-id="bb240-129">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="bb240-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bb240-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb240-130">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
