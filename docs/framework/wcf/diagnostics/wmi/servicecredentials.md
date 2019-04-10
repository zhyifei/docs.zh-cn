---
title: ServiceCredentials
ms.date: 03/30/2017
ms.assetid: 9c780793-4785-46f7-add9-ac1ebeadb614
ms.openlocfilehash: d9563bd3bfe067ad83bfa03e7c6375a9db933f14
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230923"
---
# <a name="servicecredentials"></a><span data-ttu-id="0351d-102">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="0351d-102">ServiceCredentials</span></span>
<span data-ttu-id="0351d-103">ServiceCredentials</span><span class="sxs-lookup"><span data-stu-id="0351d-103">ServiceCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0351d-104">语法</span><span class="sxs-lookup"><span data-stu-id="0351d-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="0351d-105">方法</span><span class="sxs-lookup"><span data-stu-id="0351d-105">Methods</span></span>  
 <span data-ttu-id="0351d-106">ServiceCredentials 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="0351d-106">The ServiceCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="0351d-107">属性</span><span class="sxs-lookup"><span data-stu-id="0351d-107">Properties</span></span>  
 <span data-ttu-id="0351d-108">ServiceCredentials 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="0351d-108">The ServiceCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="0351d-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="0351d-109">ClientCertificate</span></span>  
 <span data-ttu-id="0351d-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="0351d-110">Data type: string</span></span>  
  
 <span data-ttu-id="0351d-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0351d-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0351d-112">此服务的客户端证书身份验证和配置设置。</span><span class="sxs-lookup"><span data-stu-id="0351d-112">The client certificate authentication and provisioning settings for this service.</span></span>  
  
### <a name="issuedtokenauthentication"></a><span data-ttu-id="0351d-113">IssuedTokenAuthentication</span><span class="sxs-lookup"><span data-stu-id="0351d-113">IssuedTokenAuthentication</span></span>  
 <span data-ttu-id="0351d-114">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="0351d-114">Data type: string</span></span>  
  
 <span data-ttu-id="0351d-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0351d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0351d-116">当前颁发的此服务的令牌身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="0351d-116">The current issued token authentication settings for this service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="0351d-117">对等</span><span class="sxs-lookup"><span data-stu-id="0351d-117">Peer</span></span>  
 <span data-ttu-id="0351d-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="0351d-118">Data type: string</span></span>  
  
 <span data-ttu-id="0351d-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0351d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0351d-120">对等传输终结点要使用的当前凭据身份验证和配置设置。</span><span class="sxs-lookup"><span data-stu-id="0351d-120">The current credential authentication and provisioning settings to be used by peer transport endpoints.</span></span>  
  
### <a name="secureconversationauthentication"></a><span data-ttu-id="0351d-121">SecureConversationAuthentication</span><span class="sxs-lookup"><span data-stu-id="0351d-121">SecureConversationAuthentication</span></span>  
 <span data-ttu-id="0351d-122">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="0351d-122">Data type: string</span></span>  
  
 <span data-ttu-id="0351d-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0351d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0351d-124">指定当前安全对话设置。</span><span class="sxs-lookup"><span data-stu-id="0351d-124">Specifies the current secure conversation settings.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="0351d-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="0351d-125">ServiceCertificate</span></span>  
 <span data-ttu-id="0351d-126">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="0351d-126">Data type: string</span></span>  
  
 <span data-ttu-id="0351d-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0351d-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0351d-128">与此服务关联的证书。</span><span class="sxs-lookup"><span data-stu-id="0351d-128">The certificate associated with this service.</span></span>  
  
### <a name="usernameauthentication"></a><span data-ttu-id="0351d-129">UserNameAuthentication</span><span class="sxs-lookup"><span data-stu-id="0351d-129">UserNameAuthentication</span></span>  
 <span data-ttu-id="0351d-130">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="0351d-130">Data type: string</span></span>  
  
 <span data-ttu-id="0351d-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0351d-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0351d-132">此服务的用户名/密码设置。</span><span class="sxs-lookup"><span data-stu-id="0351d-132">The username/password settings for this service.</span></span>  
  
### <a name="windowsauthentication"></a><span data-ttu-id="0351d-133">WindowsAuthentication</span><span class="sxs-lookup"><span data-stu-id="0351d-133">WindowsAuthentication</span></span>  
 <span data-ttu-id="0351d-134">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="0351d-134">Data type: string</span></span>  
  
 <span data-ttu-id="0351d-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="0351d-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="0351d-136">此服务的 Windows 身份验证设置。</span><span class="sxs-lookup"><span data-stu-id="0351d-136">The Windows authentication settings for this service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0351d-137">要求</span><span class="sxs-lookup"><span data-stu-id="0351d-137">Requirements</span></span>  
  
|<span data-ttu-id="0351d-138">MOF</span><span class="sxs-lookup"><span data-stu-id="0351d-138">MOF</span></span>|<span data-ttu-id="0351d-139">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="0351d-139">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="0351d-140">命名空间</span><span class="sxs-lookup"><span data-stu-id="0351d-140">Namespace</span></span>|<span data-ttu-id="0351d-141">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="0351d-141">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0351d-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="0351d-142">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceCredentials>
