---
title: ServiceMetadataBehavior
ms.date: 03/30/2017
ms.assetid: 0f194476-72f1-467e-bdce-674306316e64
ms.openlocfilehash: 1d99af064205447c2f11f6f19258551c1e88d386
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956944"
---
# <a name="servicemetadatabehavior"></a><span data-ttu-id="46e2a-102">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="46e2a-102">ServiceMetadataBehavior</span></span>
<span data-ttu-id="46e2a-103">ServiceMetadataBehavior</span><span class="sxs-lookup"><span data-stu-id="46e2a-103">ServiceMetadataBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46e2a-104">语法</span><span class="sxs-lookup"><span data-stu-id="46e2a-104">Syntax</span></span>  
  
```csharp
class ServiceMetadataBehavior : Behavior  
{  
  string ExternalMetadataLocation;  
  boolean HttpGetEnabled;  
  string HttpGetUrl;  
  boolean HttpsGetEnabled;  
  string HttpsGetUrl;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="46e2a-105">方法</span><span class="sxs-lookup"><span data-stu-id="46e2a-105">Methods</span></span>  
 <span data-ttu-id="46e2a-106">ServiceMetadataBehavior 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="46e2a-106">The ServiceMetadataBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="46e2a-107">属性</span><span class="sxs-lookup"><span data-stu-id="46e2a-107">Properties</span></span>  
 <span data-ttu-id="46e2a-108">ServiceMetadataBehavior 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="46e2a-108">The ServiceMetadataBehavior class has the following properties:</span></span>  
  
### <a name="externalmetadatalocation"></a><span data-ttu-id="46e2a-109">ExternalMetadataLocation</span><span class="sxs-lookup"><span data-stu-id="46e2a-109">ExternalMetadataLocation</span></span>  
 <span data-ttu-id="46e2a-110">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="46e2a-110">Data type: string</span></span>  
  
 <span data-ttu-id="46e2a-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="46e2a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="46e2a-112">设置服务重定向元数据请求的位置。</span><span class="sxs-lookup"><span data-stu-id="46e2a-112">Sets the location to which the service redirects metadata requests.</span></span>  
  
### <a name="httpgetenabled"></a><span data-ttu-id="46e2a-113">HttpGetEnabled</span><span class="sxs-lookup"><span data-stu-id="46e2a-113">HttpGetEnabled</span></span>  
 <span data-ttu-id="46e2a-114">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="46e2a-114">Data type: boolean</span></span>  
  
 <span data-ttu-id="46e2a-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="46e2a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="46e2a-116">控制服务是否在 `HttpGetUrl` 属性控制的地址上发布其 WSDL。</span><span class="sxs-lookup"><span data-stu-id="46e2a-116">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httpgeturl"></a><span data-ttu-id="46e2a-117">HttpGetUrl</span><span class="sxs-lookup"><span data-stu-id="46e2a-117">HttpGetUrl</span></span>  
 <span data-ttu-id="46e2a-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="46e2a-118">Data type: string</span></span>  
  
 <span data-ttu-id="46e2a-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="46e2a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="46e2a-120">设置位置，在该位置发布服务 WSDL 以便使用 HTTP 进行检索。</span><span class="sxs-lookup"><span data-stu-id="46e2a-120">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpsgetenabled"></a><span data-ttu-id="46e2a-121">HttpsGetEnabled</span><span class="sxs-lookup"><span data-stu-id="46e2a-121">HttpsGetEnabled</span></span>  
 <span data-ttu-id="46e2a-122">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="46e2a-122">Data type: boolean</span></span>  
  
 <span data-ttu-id="46e2a-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="46e2a-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="46e2a-124">控制服务是否在 `HttpsGetUrl` 属性控制的地址上通过 HTTPS 发布其 WSDL。</span><span class="sxs-lookup"><span data-stu-id="46e2a-124">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpsgeturl"></a><span data-ttu-id="46e2a-125">HttpsGetUrl</span><span class="sxs-lookup"><span data-stu-id="46e2a-125">HttpsGetUrl</span></span>  
 <span data-ttu-id="46e2a-126">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="46e2a-126">Data type: string</span></span>  
  
 <span data-ttu-id="46e2a-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="46e2a-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="46e2a-128">设置位置，在该位置发布服务 WSDL 以便使用 HTTPS 进行检索。</span><span class="sxs-lookup"><span data-stu-id="46e2a-128">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46e2a-129">要求</span><span class="sxs-lookup"><span data-stu-id="46e2a-129">Requirements</span></span>  
  
|<span data-ttu-id="46e2a-130">MOF</span><span class="sxs-lookup"><span data-stu-id="46e2a-130">MOF</span></span>|<span data-ttu-id="46e2a-131">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="46e2a-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="46e2a-132">命名空间</span><span class="sxs-lookup"><span data-stu-id="46e2a-132">Namespace</span></span>|<span data-ttu-id="46e2a-133">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="46e2a-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="46e2a-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="46e2a-134">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceMetadataBehavior>
