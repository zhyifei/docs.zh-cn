---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
ms.openlocfilehash: 30679e1f67c6943bf674a6bbd8bf12be090765a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "59979129"
---
# <a name="servicesecurityauditbehavior"></a><span data-ttu-id="ab660-102">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="ab660-102">ServiceSecurityAuditBehavior</span></span>
<span data-ttu-id="ab660-103">ServiceSecurityAuditBehavior</span><span class="sxs-lookup"><span data-stu-id="ab660-103">ServiceSecurityAuditBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab660-104">语法</span><span class="sxs-lookup"><span data-stu-id="ab660-104">Syntax</span></span>  
  
```csharp  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ab660-105">方法</span><span class="sxs-lookup"><span data-stu-id="ab660-105">Methods</span></span>  
 <span data-ttu-id="ab660-106">ServiceSecurityAuditBehavior 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="ab660-106">The ServiceSecurityAuditBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ab660-107">属性</span><span class="sxs-lookup"><span data-stu-id="ab660-107">Properties</span></span>  
 <span data-ttu-id="ab660-108">ServiceSecurityAuditBehavior 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="ab660-108">The ServiceSecurityAuditBehavior class has the following properties:</span></span>  
  
### <a name="auditloglocation"></a><span data-ttu-id="ab660-109">AuditLogLocation</span><span class="sxs-lookup"><span data-stu-id="ab660-109">AuditLogLocation</span></span>  
 <span data-ttu-id="ab660-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="ab660-110">Data type: string</span></span>  
  
 <span data-ttu-id="ab660-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ab660-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ab660-112">审核日志的位置。</span><span class="sxs-lookup"><span data-stu-id="ab660-112">The location of the audit log.</span></span>  
  
### <a name="messageauthenticationauditlevel"></a><span data-ttu-id="ab660-113">MessageAuthenticationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="ab660-113">MessageAuthenticationAuditLevel</span></span>  
 <span data-ttu-id="ab660-114">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="ab660-114">Data type: string</span></span>  
  
 <span data-ttu-id="ab660-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ab660-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ab660-116">用于记录审核事件的消息身份验证级别的类型。</span><span class="sxs-lookup"><span data-stu-id="ab660-116">The type of message authentication level that is used to log audit events.</span></span>  
  
### <a name="serviceauthorizationauditlevel"></a><span data-ttu-id="ab660-117">ServiceAuthorizationAuditLevel</span><span class="sxs-lookup"><span data-stu-id="ab660-117">ServiceAuthorizationAuditLevel</span></span>  
 <span data-ttu-id="ab660-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="ab660-118">Data type: string</span></span>  
  
 <span data-ttu-id="ab660-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ab660-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ab660-120">审核日志中记录的授权事件类型。</span><span class="sxs-lookup"><span data-stu-id="ab660-120">The types of authorization events that are recorded in the audit log.</span></span>  
  
### <a name="suppressauditfailure"></a><span data-ttu-id="ab660-121">SuppressAuditFailure</span><span class="sxs-lookup"><span data-stu-id="ab660-121">SuppressAuditFailure</span></span>  
 <span data-ttu-id="ab660-122">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="ab660-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="ab660-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ab660-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ab660-124">一个 boolean 值，指定取消显示审核日志写入失败的行为。</span><span class="sxs-lookup"><span data-stu-id="ab660-124">A boolean value that specifies the behavior for suppressing failures of writing to the audit log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ab660-125">要求</span><span class="sxs-lookup"><span data-stu-id="ab660-125">Requirements</span></span>  
  
|<span data-ttu-id="ab660-126">MOF</span><span class="sxs-lookup"><span data-stu-id="ab660-126">MOF</span></span>|<span data-ttu-id="ab660-127">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="ab660-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ab660-128">命名空间</span><span class="sxs-lookup"><span data-stu-id="ab660-128">Namespace</span></span>|<span data-ttu-id="ab660-129">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="ab660-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ab660-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="ab660-130">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
