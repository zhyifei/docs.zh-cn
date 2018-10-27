---
title: ServiceDebugBehavior
ms.date: 03/30/2017
ms.assetid: a5ec9061-1e95-43fb-b0d9-dbd0a7bc3c44
ms.openlocfilehash: 68b2350f257bc95d8e17f4b9049d67c7f67becae
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/19/2018
ms.locfileid: "49452857"
---
# <a name="servicedebugbehavior"></a><span data-ttu-id="bcf0c-102">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="bcf0c-102">ServiceDebugBehavior</span></span>
<span data-ttu-id="bcf0c-103">ServiceDebugBehavior</span><span class="sxs-lookup"><span data-stu-id="bcf0c-103">ServiceDebugBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcf0c-104">语法</span><span class="sxs-lookup"><span data-stu-id="bcf0c-104">Syntax</span></span>  
  
```csharp
class ServiceDebugBehavior : Behavior  
{  
  boolean HttpHelpPageEnabled;  
  string HttpHelpPageUrl;  
  boolean HttpsHelpPageEnabled;  
  string HttpsHelpPageUrl;  
  boolean IncludeExceptionDetailInFaults;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="bcf0c-105">方法</span><span class="sxs-lookup"><span data-stu-id="bcf0c-105">Methods</span></span>  
 <span data-ttu-id="bcf0c-106">ServiceDebugBehavior 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="bcf0c-106">The ServiceDebugBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bcf0c-107">属性</span><span class="sxs-lookup"><span data-stu-id="bcf0c-107">Properties</span></span>  
 <span data-ttu-id="bcf0c-108">ServiceDebugBehavior 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="bcf0c-108">The ServiceDebugBehavior class has the following properties:</span></span>  
  
### <a name="httphelppageenabled"></a><span data-ttu-id="bcf0c-109">HttpHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="bcf0c-109">HttpHelpPageEnabled</span></span>  
 <span data-ttu-id="bcf0c-110">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="bcf0c-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="bcf0c-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="bcf0c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bcf0c-112">控制服务是否在 `HttpGetUrl` 属性控制的地址上发布其 WSDL。</span><span class="sxs-lookup"><span data-stu-id="bcf0c-112">Controls whether the service publishes its WSDL at the address controlled by the `HttpGetUrl` attribute.</span></span>  
  
### <a name="httphelppageurl"></a><span data-ttu-id="bcf0c-113">HttpHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="bcf0c-113">HttpHelpPageUrl</span></span>  
 <span data-ttu-id="bcf0c-114">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="bcf0c-114">Data type: string</span></span>  
  
 <span data-ttu-id="bcf0c-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="bcf0c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bcf0c-116">设置位置，在该位置发布服务 WSDL 以便使用 HTTP 进行检索。</span><span class="sxs-lookup"><span data-stu-id="bcf0c-116">Sets the location at which the service WSDL is published for retrieval using HTTP.</span></span>  
  
### <a name="httpshelppageenabled"></a><span data-ttu-id="bcf0c-117">HttpsHelpPageEnabled</span><span class="sxs-lookup"><span data-stu-id="bcf0c-117">HttpsHelpPageEnabled</span></span>  
 <span data-ttu-id="bcf0c-118">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="bcf0c-118">Data type: boolean</span></span>  
  
 <span data-ttu-id="bcf0c-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="bcf0c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bcf0c-120">控制服务是否在 `HttpsGetUrl` 属性控制的地址上通过 HTTPS 发布其 WSDL。</span><span class="sxs-lookup"><span data-stu-id="bcf0c-120">Controls whether the service publishes its WSDL over HTTPS at the address controlled by the `HttpsGetUrl` attribute.</span></span>  
  
### <a name="httpshelppageurl"></a><span data-ttu-id="bcf0c-121">HttpsHelpPageUrl</span><span class="sxs-lookup"><span data-stu-id="bcf0c-121">HttpsHelpPageUrl</span></span>  
 <span data-ttu-id="bcf0c-122">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="bcf0c-122">Data type: string</span></span>  
  
 <span data-ttu-id="bcf0c-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="bcf0c-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bcf0c-124">设置位置，在该位置发布服务 WSDL 以便使用 HTTPS 进行检索。</span><span class="sxs-lookup"><span data-stu-id="bcf0c-124">Sets the location at which the service WSDL is published for retrieval using HTTPS.</span></span>  
  
### <a name="includeexceptiondetailinfaults"></a><span data-ttu-id="bcf0c-125">IncludeExceptionDetailInFaults</span><span class="sxs-lookup"><span data-stu-id="bcf0c-125">IncludeExceptionDetailInFaults</span></span>  
 <span data-ttu-id="bcf0c-126">数据类型：Boolean</span><span class="sxs-lookup"><span data-stu-id="bcf0c-126">Data type: boolean</span></span>  
  
 <span data-ttu-id="bcf0c-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="bcf0c-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bcf0c-128">指定是否在返回给客户端的 SOAP 错误详细信息中包含托管异常信息以供调试。</span><span class="sxs-lookup"><span data-stu-id="bcf0c-128">Specifies whether to include managed exception information in the detail of SOAP faults returned to the clients for debugging purposes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcf0c-129">要求</span><span class="sxs-lookup"><span data-stu-id="bcf0c-129">Requirements</span></span>  
  
|<span data-ttu-id="bcf0c-130">MOF</span><span class="sxs-lookup"><span data-stu-id="bcf0c-130">MOF</span></span>|<span data-ttu-id="bcf0c-131">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="bcf0c-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bcf0c-132">命名空间</span><span class="sxs-lookup"><span data-stu-id="bcf0c-132">Namespace</span></span>|<span data-ttu-id="bcf0c-133">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="bcf0c-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bcf0c-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="bcf0c-134">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceDebugBehavior>
