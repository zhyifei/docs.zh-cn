---
title: ServiceCredentials
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 73fad36b5bf14745ca70d297fa988b90d46990df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="servicecredentials"></a><span data-ttu-id="ef48c-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="ef48c-102">ServiceCredentials</span></span>
<span data-ttu-id="ef48c-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="ef48c-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef48c-104">语法</span><span class="sxs-lookup"><span data-stu-id="ef48c-104">Syntax</span></span>  
  
```  
class ServiceCredentials : Behavior  
{  
  string ClientCertificate;  
  string IssuedTokenAuthentication;  
  string Peer;  
  string SecureConversationAuthentication;  
  string ServiceCertificate;  
  string UserNameAuthentication;  
  string WindowsAuthentication;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ef48c-105">方法</span><span class="sxs-lookup"><span data-stu-id="ef48c-105">Methods</span></span>  
 <span data-ttu-id="ef48c-106">ServiceCredentials 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="ef48c-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ef48c-107">属性</span><span class="sxs-lookup"><span data-stu-id="ef48c-107">Properties</span></span>  
 <span data-ttu-id="ef48c-108">ServiceCredentials 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="ef48c-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="ef48c-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="ef48c-109">ClientCertificate</span></span>  
 <span data-ttu-id="ef48c-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="ef48c-110">Data type: string</span></span>  
  
 <span data-ttu-id="ef48c-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ef48c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ef48c-112">此服务的客户端证书身份验证和配置设置。</span><span class="sxs-lookup"><span data-stu-id="ef48c-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="ef48c-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="ef48c-113">IssuedTokenAuthentication</span></span>  
 <span data-ttu-id="ef48c-114">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="ef48c-114">Data type: string</span></span>  
  
 <span data-ttu-id="ef48c-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ef48c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ef48c-116">当前颁发的此服务的令牌身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="ef48c-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="ef48c-117">对等</span><span class="sxs-lookup"><span data-stu-id="ef48c-117">Peer</span></span>  
 <span data-ttu-id="ef48c-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="ef48c-118">Data type: string</span></span>  
  
 <span data-ttu-id="ef48c-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ef48c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ef48c-120">对等传输终结点要使用的当前凭据身份验证和配置设置。</span><span class="sxs-lookup"><span data-stu-id="ef48c-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="ef48c-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="ef48c-121">SecureConversationAuthentication</span></span>  
 <span data-ttu-id="ef48c-122">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="ef48c-122">Data type: string</span></span>  
  
 <span data-ttu-id="ef48c-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ef48c-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ef48c-124">指定当前安全对话设置。</span><span class="sxs-lookup"><span data-stu-id="ef48c-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="ef48c-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="ef48c-125">ServiceCertificate</span></span>  
 <span data-ttu-id="ef48c-126">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="ef48c-126">Data type: string</span></span>  
  
 <span data-ttu-id="ef48c-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ef48c-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ef48c-128">与此服务关联的证书。</span><span class="sxs-lookup"><span data-stu-id="ef48c-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="ef48c-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="ef48c-129">UserNameAuthentication</span></span>  
 <span data-ttu-id="ef48c-130">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="ef48c-130">Data type: string</span></span>  
  
 <span data-ttu-id="ef48c-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ef48c-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ef48c-132">此服务的用户名/密码设置。</span><span class="sxs-lookup"><span data-stu-id="ef48c-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="ef48c-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="ef48c-133">WindowsAuthentication</span></span>  
 <span data-ttu-id="ef48c-134">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="ef48c-134">Data type: string</span></span>  
  
 <span data-ttu-id="ef48c-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ef48c-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ef48c-136">此服务的 Windows 身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="ef48c-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef48c-137">惠?</span><span class="sxs-lookup"><span data-stu-id="ef48c-137">Requirements</span></span>  
  
|<span data-ttu-id="ef48c-138">MOF</span><span class="sxs-lookup"><span data-stu-id="ef48c-138">MOF</span></span>|<span data-ttu-id="ef48c-139">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="ef48c-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ef48c-140">命名空间</span><span class="sxs-lookup"><span data-stu-id="ef48c-140">Namespace</span></span>|<span data-ttu-id="ef48c-141">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="ef48c-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ef48c-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="ef48c-142">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceCredentials>
