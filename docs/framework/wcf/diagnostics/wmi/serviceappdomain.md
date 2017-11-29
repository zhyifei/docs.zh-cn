---
title: ServiceAppDomain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 36048f56c3b54447a112e6f0a457624062ce965a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="serviceappdomain"></a><span data-ttu-id="20060-102">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="20060-102">ServiceAppDomain</span></span>
<span data-ttu-id="20060-103">将服务映射到应用程序域。</span><span class="sxs-lookup"><span data-stu-id="20060-103">Maps a service to an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20060-104">语法</span><span class="sxs-lookup"><span data-stu-id="20060-104">Syntax</span></span>  
  
```  
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="20060-105">方法</span><span class="sxs-lookup"><span data-stu-id="20060-105">Methods</span></span>  
 <span data-ttu-id="20060-106">ServiceAppDomain 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="20060-106">The ServiceAppDomain class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="20060-107">属性</span><span class="sxs-lookup"><span data-stu-id="20060-107">Properties</span></span>  
 <span data-ttu-id="20060-108">ServiceAppDomain 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="20060-108">The ServiceAppDomain class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="20060-109">ref</span><span class="sxs-lookup"><span data-stu-id="20060-109">ref</span></span>  
 <span data-ttu-id="20060-110">数据类型：Service</span><span class="sxs-lookup"><span data-stu-id="20060-110">Data type: Service</span></span>  
<span data-ttu-id="20060-111">限定符：键</span><span class="sxs-lookup"><span data-stu-id="20060-111">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="20060-112">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="20060-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="20060-113">此应用程序域的服务。</span><span class="sxs-lookup"><span data-stu-id="20060-113">The service of this application domain.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="20060-114">ref</span><span class="sxs-lookup"><span data-stu-id="20060-114">ref</span></span>  
 <span data-ttu-id="20060-115">数据类型：AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="20060-115">Data type: AppDomainInfo</span></span>  
<span data-ttu-id="20060-116">限定符：键</span><span class="sxs-lookup"><span data-stu-id="20060-116">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="20060-117">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="20060-117">Access type: Read-only</span></span>  
  
 <span data-ttu-id="20060-118">包含应用程序域的属性。</span><span class="sxs-lookup"><span data-stu-id="20060-118">Contains properties of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20060-119">要求</span><span class="sxs-lookup"><span data-stu-id="20060-119">Requirements</span></span>  
  
|<span data-ttu-id="20060-120">MOF</span><span class="sxs-lookup"><span data-stu-id="20060-120">MOF</span></span>|<span data-ttu-id="20060-121">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="20060-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="20060-122">命名空间</span><span class="sxs-lookup"><span data-stu-id="20060-122">Namespace</span></span>|<span data-ttu-id="20060-123">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="20060-123">Defined in root\ServiceModel</span></span>|
