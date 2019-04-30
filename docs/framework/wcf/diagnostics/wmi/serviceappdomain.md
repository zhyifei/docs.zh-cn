---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: 05be495dbfe87e7dd14b0cfbb38b30c6f8278e6d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61957068"
---
# <a name="serviceappdomain"></a><span data-ttu-id="e0e78-102">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="e0e78-102">ServiceAppDomain</span></span>
<span data-ttu-id="e0e78-103">将服务映射到应用程序域。</span><span class="sxs-lookup"><span data-stu-id="e0e78-103">Maps a service to an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0e78-104">语法</span><span class="sxs-lookup"><span data-stu-id="e0e78-104">Syntax</span></span>  
  
```csharp
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="e0e78-105">方法</span><span class="sxs-lookup"><span data-stu-id="e0e78-105">Methods</span></span>  
 <span data-ttu-id="e0e78-106">ServiceAppDomain 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="e0e78-106">The ServiceAppDomain class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="e0e78-107">属性</span><span class="sxs-lookup"><span data-stu-id="e0e78-107">Properties</span></span>  
 <span data-ttu-id="e0e78-108">ServiceAppDomain 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="e0e78-108">The ServiceAppDomain class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="e0e78-109">ref</span><span class="sxs-lookup"><span data-stu-id="e0e78-109">ref</span></span>  
 <span data-ttu-id="e0e78-110">数据类型：服务</span><span class="sxs-lookup"><span data-stu-id="e0e78-110">Data type: Service</span></span>  
<span data-ttu-id="e0e78-111">限定符：键</span><span class="sxs-lookup"><span data-stu-id="e0e78-111">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="e0e78-112">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e0e78-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e0e78-113">此应用程序域的服务。</span><span class="sxs-lookup"><span data-stu-id="e0e78-113">The service of this application domain.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="e0e78-114">ref</span><span class="sxs-lookup"><span data-stu-id="e0e78-114">ref</span></span>  
 <span data-ttu-id="e0e78-115">数据类型：AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="e0e78-115">Data type: AppDomainInfo</span></span>  
<span data-ttu-id="e0e78-116">限定符：键</span><span class="sxs-lookup"><span data-stu-id="e0e78-116">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="e0e78-117">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="e0e78-117">Access type: Read-only</span></span>  
  
 <span data-ttu-id="e0e78-118">包含应用程序域的属性。</span><span class="sxs-lookup"><span data-stu-id="e0e78-118">Contains properties of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0e78-119">要求</span><span class="sxs-lookup"><span data-stu-id="e0e78-119">Requirements</span></span>  
  
|<span data-ttu-id="e0e78-120">MOF</span><span class="sxs-lookup"><span data-stu-id="e0e78-120">MOF</span></span>|<span data-ttu-id="e0e78-121">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="e0e78-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="e0e78-122">命名空间</span><span class="sxs-lookup"><span data-stu-id="e0e78-122">Namespace</span></span>|<span data-ttu-id="e0e78-123">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="e0e78-123">Defined in root\ServiceModel</span></span>|
