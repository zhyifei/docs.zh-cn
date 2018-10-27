---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: 26bd0c95f930bf7859ae6409d797afbb596844fa
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50180661"
---
# <a name="servicecredentials"></a><span data-ttu-id="bf463-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="bf463-102">ServiceCredentials</span></span>
<span data-ttu-id="bf463-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="bf463-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf463-104">语法</span><span class="sxs-lookup"><span data-stu-id="bf463-104">Syntax</span></span>  
  
```csharp
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
  
## <a name="methods"></a><span data-ttu-id="bf463-105">方法</span><span class="sxs-lookup"><span data-stu-id="bf463-105">Methods</span></span>  
 <span data-ttu-id="bf463-106">ServiceCredentials 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="bf463-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bf463-107">属性</span><span class="sxs-lookup"><span data-stu-id="bf463-107">Properties</span></span>  
 <span data-ttu-id="bf463-108">ServiceCredentials 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="bf463-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="bf463-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="bf463-109">ClientCertificate</span></span>  
 <span data-ttu-id="bf463-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="bf463-110">Data type: string</span></span>  
  
 <span data-ttu-id="bf463-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="bf463-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf463-112">此服务的客户端证书身份验证和配置设置。</span><span class="sxs-lookup"><span data-stu-id="bf463-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="bf463-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="bf463-113">IssuedTokenAuthentication</span></span>  
 <span data-ttu-id="bf463-114">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="bf463-114">Data type: string</span></span>  
  
 <span data-ttu-id="bf463-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="bf463-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf463-116">当前颁发的此服务的令牌身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="bf463-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="bf463-117">对等</span><span class="sxs-lookup"><span data-stu-id="bf463-117">Peer</span></span>  
 <span data-ttu-id="bf463-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="bf463-118">Data type: string</span></span>  
  
 <span data-ttu-id="bf463-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="bf463-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf463-120">对等传输终结点要使用的当前凭据身份验证和配置设置。</span><span class="sxs-lookup"><span data-stu-id="bf463-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="bf463-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="bf463-121">SecureConversationAuthentication</span></span>  
 <span data-ttu-id="bf463-122">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="bf463-122">Data type: string</span></span>  
  
 <span data-ttu-id="bf463-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="bf463-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf463-124">指定当前安全对话设置。</span><span class="sxs-lookup"><span data-stu-id="bf463-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="bf463-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="bf463-125">ServiceCertificate</span></span>  
 <span data-ttu-id="bf463-126">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="bf463-126">Data type: string</span></span>  
  
 <span data-ttu-id="bf463-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="bf463-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf463-128">与此服务关联的证书。</span><span class="sxs-lookup"><span data-stu-id="bf463-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="bf463-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="bf463-129">UserNameAuthentication</span></span>  
 <span data-ttu-id="bf463-130">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="bf463-130">Data type: string</span></span>  
  
 <span data-ttu-id="bf463-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="bf463-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf463-132">此服务的用户名/密码设置。</span><span class="sxs-lookup"><span data-stu-id="bf463-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="bf463-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="bf463-133">WindowsAuthentication</span></span>  
 <span data-ttu-id="bf463-134">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="bf463-134">Data type: string</span></span>  
  
 <span data-ttu-id="bf463-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="bf463-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bf463-136">此服务的 Windows 身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="bf463-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf463-137">要求</span><span class="sxs-lookup"><span data-stu-id="bf463-137">Requirements</span></span>  
  
|<span data-ttu-id="bf463-138">MOF</span><span class="sxs-lookup"><span data-stu-id="bf463-138">MOF</span></span>|<span data-ttu-id="bf463-139">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="bf463-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bf463-140">命名空间</span><span class="sxs-lookup"><span data-stu-id="bf463-140">Namespace</span></span>|<span data-ttu-id="bf463-141">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="bf463-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bf463-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf463-142">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceCredentials>
