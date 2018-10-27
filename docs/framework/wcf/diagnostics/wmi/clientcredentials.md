---
title: ClientCredentials
ms.date: 03/30/2017
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
ms.openlocfilehash: 8b6200f84f352d49cf142d9c8b97d1c2b36149b2
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50180895"
---
# <a name="clientcredentials"></a><span data-ttu-id="3fdaa-102">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="3fdaa-102">ClientCredentials</span></span>
<span data-ttu-id="3fdaa-103">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="3fdaa-103">ClientCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fdaa-104">语法</span><span class="sxs-lookup"><span data-stu-id="3fdaa-104">Syntax</span></span>  
  
```csharp
class ClientCredentials : Behavior  
{  
  string ClientCertificate;  
  string HttpDigest;  
  string IssuedToken;  
  string Peer;  
  string ServiceCertificate;  
  boolean SupportInteractive;  
  string UserName;  
  string Windows;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3fdaa-105">方法</span><span class="sxs-lookup"><span data-stu-id="3fdaa-105">Methods</span></span>  
 <span data-ttu-id="3fdaa-106">ClientCredentials 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-106">The ClientCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3fdaa-107">属性</span><span class="sxs-lookup"><span data-stu-id="3fdaa-107">Properties</span></span>  
 <span data-ttu-id="3fdaa-108">ClientCredentials 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="3fdaa-108">The ClientCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="3fdaa-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="3fdaa-109">ClientCertificate</span></span>  
 <span data-ttu-id="3fdaa-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="3fdaa-110">Data type: string</span></span>  
  
 <span data-ttu-id="3fdaa-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3fdaa-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3fdaa-112">客户端用来向服务验证身份的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-112">The X.509 certificate the client uses to authenticate to the service.</span></span>  
  
### <a name="httpdigest"></a><span data-ttu-id="3fdaa-113">HttpDigest</span><span class="sxs-lookup"><span data-stu-id="3fdaa-113">HttpDigest</span></span>  
 <span data-ttu-id="3fdaa-114">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="3fdaa-114">Data type: string</span></span>  
  
 <span data-ttu-id="3fdaa-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3fdaa-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3fdaa-116">当前 Http Digest 凭据。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-116">The current Http Digest credential.</span></span>  
  
### <a name="issuedtoken"></a><span data-ttu-id="3fdaa-117">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="3fdaa-117">IssuedToken</span></span>  
 <span data-ttu-id="3fdaa-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="3fdaa-118">Data type: string</span></span>  
  
 <span data-ttu-id="3fdaa-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3fdaa-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3fdaa-120">用于联系本地安全令牌服务的终结点地址和绑定。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-120">The endpoint address and binding used to contact the local security token service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="3fdaa-121">对等</span><span class="sxs-lookup"><span data-stu-id="3fdaa-121">Peer</span></span>  
 <span data-ttu-id="3fdaa-122">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="3fdaa-122">Data type: string</span></span>  
  
 <span data-ttu-id="3fdaa-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3fdaa-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3fdaa-124">对等节点用来向网格中的其他节点验证其自身身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-124">The credentials that the peer node uses to authenticate itself to other nodes in the mesh.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="3fdaa-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="3fdaa-125">ServiceCertificate</span></span>  
 <span data-ttu-id="3fdaa-126">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="3fdaa-126">Data type: string</span></span>  
  
 <span data-ttu-id="3fdaa-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3fdaa-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3fdaa-128">服务的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-128">The service's X.509 certificate.</span></span>  
  
### <a name="supportinteractive"></a><span data-ttu-id="3fdaa-129">SupportInteractive</span><span class="sxs-lookup"><span data-stu-id="3fdaa-129">SupportInteractive</span></span>  
 <span data-ttu-id="3fdaa-130">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="3fdaa-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="3fdaa-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3fdaa-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3fdaa-132">一个布尔值，指定凭据是否支持交互式协商。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-132">A Boolean value that specifies whether the credential supports interactive negotiation.</span></span>  
  
### <a name="username"></a><span data-ttu-id="3fdaa-133">UserName</span><span class="sxs-lookup"><span data-stu-id="3fdaa-133">UserName</span></span>  
 <span data-ttu-id="3fdaa-134">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="3fdaa-134">Data type: string</span></span>  
  
 <span data-ttu-id="3fdaa-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3fdaa-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3fdaa-136">客户端用来向服务验证其自身身份的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-136">The username and password the client uses to authenticate itself to the service.</span></span>  
  
### <a name="windows"></a><span data-ttu-id="3fdaa-137">Windows</span><span class="sxs-lookup"><span data-stu-id="3fdaa-137">Windows</span></span>  
 <span data-ttu-id="3fdaa-138">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="3fdaa-138">Data type: string</span></span>  
  
 <span data-ttu-id="3fdaa-139">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="3fdaa-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3fdaa-140">客户端用来向服务验证其自身身份的 Windows 凭据。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-140">The windows credentials the client uses to authenticate itself to the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fdaa-141">要求</span><span class="sxs-lookup"><span data-stu-id="3fdaa-141">Requirements</span></span>  
  
|<span data-ttu-id="3fdaa-142">MOF</span><span class="sxs-lookup"><span data-stu-id="3fdaa-142">MOF</span></span>|<span data-ttu-id="3fdaa-143">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="3fdaa-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3fdaa-144">命名空间</span><span class="sxs-lookup"><span data-stu-id="3fdaa-144">Namespace</span></span>|<span data-ttu-id="3fdaa-145">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="3fdaa-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3fdaa-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="3fdaa-146">See Also</span></span>  
 <xref:System.ServiceModel.Description.ClientCredentials>
