---
title: ClientCredentials
ms.date: 03/30/2017
ms.assetid: 41dffd6b-8f14-4fed-aefb-2a1bb168efb3
ms.openlocfilehash: aa852ff82c44a3b5009dbc70e1067face44cbbe9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486371"
---
# <a name="clientcredentials"></a><span data-ttu-id="e7581-102">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="e7581-102">ClientCredentials</span></span>
<span data-ttu-id="e7581-103">ClientCredentials</span><span class="sxs-lookup"><span data-stu-id="e7581-103">ClientCredentials</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7581-104">语法</span><span class="sxs-lookup"><span data-stu-id="e7581-104">Syntax</span></span>  
  
```  
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
  
## <a name="methods"></a><span data-ttu-id="e7581-105">方法</span><span class="sxs-lookup"><span data-stu-id="e7581-105">Methods</span></span>  
 <span data-ttu-id="e7581-106">ClientCredentials 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="e7581-106">The ClientCredentials class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e7581-107">属性</span><span class="sxs-lookup"><span data-stu-id="e7581-107">Properties</span></span>  
 <span data-ttu-id="e7581-108">ClientCredentials 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="e7581-108">The ClientCredentials class has the following properties:</span></span>  
  
### <a name="clientcertificate"></a><span data-ttu-id="e7581-109">ClientCertificate</span><span class="sxs-lookup"><span data-stu-id="e7581-109">ClientCertificate</span></span>  
 <span data-ttu-id="e7581-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="e7581-110">Data type: string</span></span>  
  
 <span data-ttu-id="e7581-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e7581-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e7581-112">客户端用来向服务验证身份的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="e7581-112">The X.509 certificate the client uses to authenticate to the service.</span></span>  
  
### <a name="httpdigest"></a><span data-ttu-id="e7581-113">HttpDigest</span><span class="sxs-lookup"><span data-stu-id="e7581-113">HttpDigest</span></span>  
 <span data-ttu-id="e7581-114">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="e7581-114">Data type: string</span></span>  
  
 <span data-ttu-id="e7581-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e7581-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e7581-116">当前 Http Digest 凭据。</span><span class="sxs-lookup"><span data-stu-id="e7581-116">The current Http Digest credential.</span></span>  
  
### <a name="issuedtoken"></a><span data-ttu-id="e7581-117">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="e7581-117">IssuedToken</span></span>  
 <span data-ttu-id="e7581-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="e7581-118">Data type: string</span></span>  
  
 <span data-ttu-id="e7581-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e7581-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e7581-120">用于联系本地安全令牌服务的终结点地址和绑定。</span><span class="sxs-lookup"><span data-stu-id="e7581-120">The endpoint address and binding used to contact the local security token service.</span></span>  
  
### <a name="peer"></a><span data-ttu-id="e7581-121">对等</span><span class="sxs-lookup"><span data-stu-id="e7581-121">Peer</span></span>  
 <span data-ttu-id="e7581-122">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="e7581-122">Data type: string</span></span>  
  
 <span data-ttu-id="e7581-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e7581-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e7581-124">对等节点用来向网格中的其他节点验证其自身身份的凭据。</span><span class="sxs-lookup"><span data-stu-id="e7581-124">The credentials that the peer node uses to authenticate itself to other nodes in the mesh.</span></span>  
  
### <a name="servicecertificate"></a><span data-ttu-id="e7581-125">ServiceCertificate</span><span class="sxs-lookup"><span data-stu-id="e7581-125">ServiceCertificate</span></span>  
 <span data-ttu-id="e7581-126">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="e7581-126">Data type: string</span></span>  
  
 <span data-ttu-id="e7581-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e7581-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e7581-128">服务的 X.509 证书。</span><span class="sxs-lookup"><span data-stu-id="e7581-128">The service's X.509 certificate.</span></span>  
  
### <a name="supportinteractive"></a><span data-ttu-id="e7581-129">SupportInteractive</span><span class="sxs-lookup"><span data-stu-id="e7581-129">SupportInteractive</span></span>  
 <span data-ttu-id="e7581-130">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="e7581-130">Data type: boolean</span></span>  
  
 <span data-ttu-id="e7581-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e7581-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e7581-132">一个布尔值，指定凭据是否支持交互式协商。</span><span class="sxs-lookup"><span data-stu-id="e7581-132">A Boolean value that specifies whether the credential supports interactive negotiation.</span></span>  
  
### <a name="username"></a><span data-ttu-id="e7581-133">UserName</span><span class="sxs-lookup"><span data-stu-id="e7581-133">UserName</span></span>  
 <span data-ttu-id="e7581-134">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="e7581-134">Data type: string</span></span>  
  
 <span data-ttu-id="e7581-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e7581-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e7581-136">客户端用来向服务验证其自身身份的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="e7581-136">The username and password the client uses to authenticate itself to the service.</span></span>  
  
### <a name="windows"></a><span data-ttu-id="e7581-137">Windows</span><span class="sxs-lookup"><span data-stu-id="e7581-137">Windows</span></span>  
 <span data-ttu-id="e7581-138">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="e7581-138">Data type: string</span></span>  
  
 <span data-ttu-id="e7581-139">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e7581-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e7581-140">客户端用来向服务验证其自身身份的 Windows 凭据。</span><span class="sxs-lookup"><span data-stu-id="e7581-140">The windows credentials the client uses to authenticate itself to the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7581-141">要求</span><span class="sxs-lookup"><span data-stu-id="e7581-141">Requirements</span></span>  
  
|<span data-ttu-id="e7581-142">MOF</span><span class="sxs-lookup"><span data-stu-id="e7581-142">MOF</span></span>|<span data-ttu-id="e7581-143">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="e7581-143">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e7581-144">命名空间</span><span class="sxs-lookup"><span data-stu-id="e7581-144">Namespace</span></span>|<span data-ttu-id="e7581-145">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="e7581-145">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="e7581-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="e7581-146">See Also</span></span>  
 <xref:System.ServiceModel.Description.ClientCredentials>
