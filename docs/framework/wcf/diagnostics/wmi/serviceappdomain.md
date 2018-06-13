---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: aef0a0da9d107b92d9d3017968d5554205a6fd71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485663"
---
# <a name="serviceappdomain"></a><span data-ttu-id="dc5cc-102">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="dc5cc-102">ServiceAppDomain</span></span>
<span data-ttu-id="dc5cc-103">将服务映射到应用程序域。</span><span class="sxs-lookup"><span data-stu-id="dc5cc-103">Maps a service to an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc5cc-104">语法</span><span class="sxs-lookup"><span data-stu-id="dc5cc-104">Syntax</span></span>  
  
```  
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="dc5cc-105">方法</span><span class="sxs-lookup"><span data-stu-id="dc5cc-105">Methods</span></span>  
 <span data-ttu-id="dc5cc-106">ServiceAppDomain 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="dc5cc-106">The ServiceAppDomain class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="dc5cc-107">属性</span><span class="sxs-lookup"><span data-stu-id="dc5cc-107">Properties</span></span>  
 <span data-ttu-id="dc5cc-108">ServiceAppDomain 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="dc5cc-108">The ServiceAppDomain class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="dc5cc-109">ref</span><span class="sxs-lookup"><span data-stu-id="dc5cc-109">ref</span></span>  
 <span data-ttu-id="dc5cc-110">数据类型：Service</span><span class="sxs-lookup"><span data-stu-id="dc5cc-110">Data type: Service</span></span>  
<span data-ttu-id="dc5cc-111">限定符：键</span><span class="sxs-lookup"><span data-stu-id="dc5cc-111">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="dc5cc-112">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="dc5cc-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc5cc-113">此应用程序域的服务。</span><span class="sxs-lookup"><span data-stu-id="dc5cc-113">The service of this application domain.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="dc5cc-114">ref</span><span class="sxs-lookup"><span data-stu-id="dc5cc-114">ref</span></span>  
 <span data-ttu-id="dc5cc-115">数据类型：AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="dc5cc-115">Data type: AppDomainInfo</span></span>  
<span data-ttu-id="dc5cc-116">限定符：键</span><span class="sxs-lookup"><span data-stu-id="dc5cc-116">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="dc5cc-117">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="dc5cc-117">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dc5cc-118">包含应用程序域的属性。</span><span class="sxs-lookup"><span data-stu-id="dc5cc-118">Contains properties of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc5cc-119">要求</span><span class="sxs-lookup"><span data-stu-id="dc5cc-119">Requirements</span></span>  
  
|<span data-ttu-id="dc5cc-120">MOF</span><span class="sxs-lookup"><span data-stu-id="dc5cc-120">MOF</span></span>|<span data-ttu-id="dc5cc-121">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="dc5cc-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="dc5cc-122">命名空间</span><span class="sxs-lookup"><span data-stu-id="dc5cc-122">Namespace</span></span>|<span data-ttu-id="dc5cc-123">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="dc5cc-123">Defined in root\ServiceModel</span></span>|
